# INTRODUÇÃO

Guia de referência para assuntos relacionados a agents de programação do tipo CLI (Command Line Interface).

---

## LOGIN/LOGOUT

```shell
<agent> login
<agent> login status
<agent> logout
```


## COMANDOS BÁSICOS

```
<nome>: No terminal para iniciar.
/help: Mostra os comandos disponíveis.
/status: Status atual.
/model: Lista modelos disponíveis.
/model <número>: Traca para o modelo de acordo com o número correspondente.
/model <nome>: Idem ao anterior, mas aqui é pelo nome ao invés do número.
/model status: Status do modelo.
/provider: Lista os providers e permite alterar.
/tools: Acesso as ferramentas disponíveis.
/context detail: Mostra quantos tokens estão sendo consumidos.
/export: Exporta conversas.
/btw <pergunta>: Faz uma pergunta temporária sem poluir a conversa principal.
/resume: Lista histórico de conversas.
/resume <ID_DA_SESSAO>: Abre a sessão relacionada a ID.
/resume --last	: Abre a última conversa.
```
