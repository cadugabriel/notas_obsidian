# GUNICORN

O Gunicorn (WSGI Application Server) é um serviço de aplicação. Muito utilizado em aplicações Python Flask.

----

## Comando de Inicialização Completo

```bash
gunicorn --chdir app app:app -w 2 --threads 2 -b 0.0.0.0:8001 --log-level=debug
```

## Anatomia dos Parâmetros

| **Parâmetro / Flag** | **Exemplo**    | **Descrição Técnica**                                                       |
| -------------------- | -------------- | --------------------------------------------------------------------------- |
| `--chdir`            | `app`          | Define o diretório de trabalho onde o Gunicorn deve procurar o código.      |
| **Módulo:Aplicação** | `app:app`      | O primeiro é o nome do arquivo (`app.py`), o segundo é a variável do Flask. |
| `-w`                 | `2`            | Número de processos _workers_ ativos (recomendado entre 2 e 4 por core).    |
| `--threads`          | `2`            | Quantidade de threads simultâneas por worker (recomendado entre 2 e 4).     |
| `-b`                 | `0.0.0.0:8001` | Faz o bind do socket, definindo o endereço IP e a porta de escuta.          |
| `--log-level`        | `debug`        | Nível de verbosidade do log (útil para homologação e troubleshooting).      |

> 📁 **Arquivo de Configuração Permanente:** Para não precisar digitar os parâmetros no terminal, você pode centralizá-los criando um arquivo chamado `config_gunicorn.py`.

> 🔗 A documentação detalhada da estrutura deste arquivo pode ser consultada no [Gist de Referência do Gunicorn](https://gist.github.com/HacKanCuBa/275bfca09d614ee9370727f5f40dab9e).
