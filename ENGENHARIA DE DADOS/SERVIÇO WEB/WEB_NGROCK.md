# Ngrok

Serviço  para criação de Túneis Públicos Locais:

---

## Guia Passo a Passo de Configuração

```
# 1. Downdload
https://dashboard.ngrok.com/get-started/setup/windows

# 2. Inicialização
Execute o arquivo `ngrok.exe` (um prompt de comando dedicado será aberto)

# 3. Autenticação
Adicione seu token de segurança à configuração local. | ```bash<br>ngrok config add-authtoken <seu_token_aqui>

# 4. Exposição
Crie o túnel público apontando para sua aplicação. | ```bash<br>ngrok http http://<IP_LOCAL>:<PORTA><br>
```

## 💡 Dicas de Uso

* **Caso sua aplicação esteja rodando na sua própria máquina (localhost):** No passo 4, você pode simplificar o comando informando apenas a porta, como por exemplo: `ngrok http 8000`.

* **Acompanhamento de Tráfego:** Após iniciar o túnel, o terminal do Ngrok exibirá uma URL pública (HTTP e HTTPS). Você também pode monitorar as requisições em tempo real acessando a interface web local que ele disponibiliza (geralmente no endereço `http://127.0.0.1:4040`).

