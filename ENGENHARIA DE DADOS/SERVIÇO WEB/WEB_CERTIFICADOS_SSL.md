# Implementação de Segurança com Certificados SSL (OpenSSL)

Geração de chaves criptográficas e certificados autoadsinados eficientes para criptografia de tráfego de dados.

```BASH

# 1. Gerar o par de chaves e o certificado X.509 utilizando curva elíptica prime256v1 (Validade de 10 anos)

openssl req -x509 -nodes -days 3650 -newkey ec:<(openssl ecparam -name prime256v1) -keyout private_key.pem -out certificate.pem

# 2. Converter o certificado gerado para o formato DER (.crt)

openssl x509 -outform der -in certificate.pem -ou

```