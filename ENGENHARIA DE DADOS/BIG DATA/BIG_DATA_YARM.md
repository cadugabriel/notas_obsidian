# YARM

Notas relacionas ao serviço YARM

---
## Gerenciamento de Filas e Processos no YARN

| **Escopo da Operação** | **Comando YARN**                            | **Objetivo**                                                             |
| ---------------------- | ------------------------------------------- | ------------------------------------------------------------------------ |
| **Listar Filas**       | `yarn application -list`                    | Retorna a lista de filas e aplicações ativas no gerenciador de recursos. |
| **Listar Processos**   | `yarn top`                                  | Exibe em tempo real o consumo de recursos (CPU/Memória) por processo.    |
| **Matar Processo**     | `yarn application -kill <<id_do_processo>>` | Finaliza forçadamente uma aplicação no cluster através de seu ID.        |
