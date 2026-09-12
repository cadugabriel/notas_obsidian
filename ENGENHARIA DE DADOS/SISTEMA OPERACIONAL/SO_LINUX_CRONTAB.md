# CRONTAB

Notas relacionas ao serviço CronTAB

---

## Comandos de Gerenciamento do Crontab

| COMANDO              | DESCRIÇÃO                                                             |
| -------------------- | --------------------------------------------------------------------- |
| crontab -e           | Abre o editor para modificar os agendamentos do usuário atual         |
| crontab -u <user> -e | Abre o editor para agendamentos de um usuário específico              |
| crontab -l           | Lista na tela todas as tarefas agendadas para o usuário logado        |
| crontab -u <user> -l | Lista as tarefas ativas pertencentes ao usuário passado como parâmetr |

## Estrutura Base de Configuração (As 6 Colunas)

```Plaintext
* * * * * /caminho/script.sh
─── ─── ─── ─── ─── ──────────────────
│ │ │ │ │ │
│ │ │ │ │ └─                    C6: Comando ou Script de execução
│ │ │ │ └──────────────         C5: Dia da Semana (0 a 6) [7 = Domingo]
│ │ │ └──────────────────       C4: Mês do Ano (1 a 12 ou jan a dec)
│ │ └──────────────────────     C3: Dia do Mês (1 a 31)
│ └──────────────────────────   C2: Hora do Dia (0 a 23)
└────────────────────────────── C1: Minutos (0 a 59)
```


## Operadores Especiais para Regras de Tempo

- `*` (Asterisco): Representa "qualquer valor" ou executar sempre.
- `,` (Vírgula): Lista valores explícitos e separados. Ex: `1,3,5` na coluna de horas.
- `-` (Hífen): Define intervalos contínuos de tempo. Ex: `1-5` na coluna da semana (segunda a sexta).
- `/` (Barra): Especifica intervalos de salto incremental. Ex: `1-9/2` no campo de minutos é igual a `1,3,5,7,9`.


## Políticas de Controle de Acesso e Segurança

  As regras de permissão para execução e edição de agendamentos são definidas nos seguintes arquivos:

- `/etc/cron.allow`: Se o arquivo existir, **apenas** os usuários listados nele poderão rodar o crontab.
- `/etc/cron.deny`: Os usuários listados aqui serão **bloqueados** de usar o serviço.
- **Regra Sem Arquivos:** Se nenhum dos dois arquivos de política existir no sistema, apenas o usuário **root** terá acesso para gerenciar o crontab.
- **Regra de Conflito:** Caso um usuário seja cadastrado simultaneamente em ambos os arquivos, o sistema dará permissão a ele.


## Monitoramento e Logs de Execução

Os agendamentos de usuários ficam salvos em `/var/spool/cron/crontabs/`, enquanto os agendamentos macros/globais do sistema ficam concentrados em `/etc/crontab`. 

⚠️ **Dica de Bug Antigo:** Certifique-se de que o arquivo do crontab termine sempre com uma **linha em branco** (um caractere de quebra de linha após o último script). Isso evita falhas de leitura crônicas na ferramenta.
Para extrair e monitorar apenas as execuções das tarefas agendadas em segundo plano:

```Bash
cat /var/log/syslog | grep CRON >> /tmp/cron.log
```
