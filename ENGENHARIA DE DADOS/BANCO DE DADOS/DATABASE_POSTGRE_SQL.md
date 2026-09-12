# 🐘 PostgreSQL

Guia rápido de referência para manipulação de variáveis em tempo de execução, tratamento de conflitos em chaves primárias e blocos procedurais PL/pgSQL.

---

## 1. Variáveis de Sessão em Escopo de Conexão

Ideal para passar parâmetros globais temporários para views ou queries sem precisar de tabelas físicas.

| Função                 | Sintaxe PostgreSQL                             | Descrição                                                |
| :--------------------- | :--------------------------------------------- | :------------------------------------------------------- |
| **Definir Variável**   | `SET SESSION var.nome_variavel = 'valor';`     | Cria ou altera uma variável customizada na sessão atual. |
| **Recuperar Variável** | `SELECT current_setting('var.nome_variavel');` | Lê o valor da variável definida na sessão.               |

### Exemplo Prático:

```sql

-- Definindo as variáveis na sessão atual
SET SESSION var.nome = 'XXXXX';
SET SESSION var.idade = '999';

  
-- Consultando os valores armazenados
SELECT
current_setting('var.nome') AS NOME,
current_setting('var.idade') AS IDADE;

```