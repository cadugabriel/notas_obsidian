# INTRODUÇÃO

Guia de referência para instalação.

---
# 🐳 INSTALAÇÃO DOCKER


Siga os passos abaixo sequencialmente no terminal para instalar o Docker Engine e o Docker Compose.

## 1. Atualizar o Sistema

```bash
sudo apt update && sudo apt upgrade -y
```

## 2. Instalar Pré-requisitos Técnicos

```bash
sudo apt-get install curl apt-transport-https ca-certificates software-properties-common -y
```

> 📑 **Glossário dos pacotes:**
> - `apt-transport-https`: Permite ao gerenciador de pacotes transferir dados via protocolo seguro HTTPS.
> 
> - `ca-certificates`: Permite que o sistema e navegadores verifiquem chaves e certificados de segurança.
> 
>- `curl`: Utilitário de linha de comando para transferência e download de dados por URLs.
>
>- `software-properties-common`: Adiciona abstrações e scripts para gerenciar repositórios independentes.

## 3. Configurar Chaves e Repositórios Oficiais

```Bash
# Adicionar a chave pública GPG do Docker
curl -fsSL [https://download.docker.com/linux/ubuntu/gpg](https://download.docker.com/linux/ubuntu/gpg) | sudo apt-key add -


# Adicionar o repositório oficial estável
sudo add-apt-repository "deb [arch=amd64] [https://download.docker.com/linux/ubuntu](https://download.docker.com/linux/ubuntu) $(lsb_release -cs) stable"

# Sincronizar as novas fontes de repositório
sudo apt update
```

## 4. Validar Origem e Instalar o Docker-CE

Antes de baixar, garanta que a instalação virá do repositório oficial do Docker (e não do repositório padrão do Ubuntu):

```Bash
apt-cache policy docker-ce
```

_A saída deve apontar para as linhas estáveis de pacotes fornecidas por `download.docker.com`._ Se estiver tudo correto, instale e verifique o serviço:

```Bash
# Instalar o Docker Community Edition (CE)
sudo apt install docker-ce -y

# Validar se o daemon do Docker está ativo e rodando
sudo systemctl status docker
```

## 5. Configuração de Pós-Instalação (Opcional)

Para executar comandos do docker sem precisar digitar `sudo` antes de cada instrução:

```Bash
sudo usermod -aG docker $(whoami)
```

_Nota: É necessário deslogar e logar novamente no terminal para que a alteração de grupo faça efeito._

  ---

#  INSTALAÇÃO DOCKER COMPOSE

## 1. Instalação Manual do Docker Compose (v2)

```Bash
# Baixar o binário executável
sudo curl -L "[https://github.com/docker/compose/releases/download/v2.5.0/docker-compose-$(uname](https://github.com/docker/compose/releases/download/v2.5.0/docker-compose-$(uname) -s)-$(uname -m)" -o /usr/local/bin/docker-compose

# Aplicar permissão de execução ao arquivo binário
sudo chmod +x /usr/local/bin/docker-compose

# Validar se o compose está operacional
docker-compose --version
```

## 2. Teste de Validação Rápida

Valide se o ecossistema está conseguindo se comunicar com o Docker Hub e isolar processos simulando a imagem padrão de teste:

```Bash
sudo docker run hello-world
```

## 3. Processo de Desinstalação Completa (Expurgo)

Para remover completamente o Docker, suas dependências e todos os dados associados do seu servidor Linux:

```Bash

# Liste todos os pacotes relacionados que estão instalados no sistema:
dpkg -l | grep -i docker

# Remova os pacotes principais e seus respectivos arquivos de configuração permanente:
sudo apt-get purge -y docker-engine docker docker.io docker-ce docker-ce-cli docker-compose-plugin

# Exclua pacotes órfãos remanescentes que não possuem utilidade após a remoção:
sudo apt-get autoremove -y --purge docker-engine docker docker.io docker-ce docker-compose-plugin
```
