# Nginx

É um proxy reverso.

---

## Arquitetura

```
[ REQUISIÇÕES WEB ] <-----> Nginx (Porta 80/443) <-----> Gunicorn (Porta 8000) <-----> Flask App
```

## Configuração Passo a Passo no Ubuntu

```BASH
# 1.Atualizar os repositórios locais do sistema operacional:**
sudo apt-get update

# 2. Instalar o servidor web Nginx
sudo apt-get install nginx

# 3. Remover os arquivos de blocos de servidor padrões (Default):
sudo rm /etc/nginx/sites-enabled/default
sudo rm /etc/nginx/sites-available/default

# 4. Criar e dar permissão ao arquivo de configuração da sua aplicação:
sudo touch /etc/nginx/sites-available/myapp.com
sudo chown -R $USER:$USER /etc/nginx/sites-available/myapp.com

# 5. Acessar o diretório de configurações disponíveis:
cd /etc/nginx/sites-available/

# 6. Editar o arquivo `myapp.com`** inserindo o bloco abaixo para direcionar as requisições da porta 80 para a porta local do Flask/Gunicorn:
server {
		listen 80; # Porta HTTP padrão que irá responder publicamente
		location {
            proxy_pass [http://127.0.0.1:8000/](http://127.0.0.1:8000/); # Endereço local onde o Gunicorn está rodando
        }
}

# 7. Criar o link simbólico (_symlink_) para ativar o site no Nginx:
sudo ln -f -s /etc/nginx/sites-available/myapp.com /etc/nginx/sites-enabled/myapp.com

# 8. Reiniciar o serviço do Nginx para aplicar as alterações:
sudo service nginx restart
```

> 🌐 _Teste de validação:_ Insira o IP público ou local do seu servidor em um navegador web para garantir que a tela padrão de boas-vindas do Nginx seja exibida.