# 🦅 Apache Phoenix

Guia de referência rápida de comandos internos do Sqlline para Apache Phoenix, incluindo formatos de saída e exportação de dados.

---

## 1. Comandos de Inspeção de Metadados

| Função                   | Comando Phoenix / Sqlline       | Descrição                                                  |
| :----------------------- | :------------------------------ | :--------------------------------------------------------- |
| **Listar Tabelas**       | `!table`                        | Lista todas as tabelas e views disponíveis no banco.       |
| **Ver Estrutura (DDL)**  | `!describe <nome_da_tabela>`    | Exibe as colunas, tipos de dados e a estrutura da tabela.  |
| **Ver Chaves Primárias** | `!primarykeys <nome_da_tabela>` | Mostra quais colunas compõem a Primary Key (PK) da tabela. |

## 2. Configuração de Formatos de Saída (`!outputformat`)

| Comando de Saída            | Tipo de Formatação              | Ideal Para                                               |
| :-------------------------- | :------------------------------ | :------------------------------------------------------- |
| `!outputformat table`       | Tabela Gráfica Padrão           | Leitura rápida no terminal (Layout em grade).            |
| `!outputformat vertical`    | Chave/Valor Vertical            | Visualizar tabelas com muitas colunas sem quebrar linha. |
| `!outputformat csv`         | Valores Separados por Vírgula   | Exportações básicas e scripts de automação.              |
| `!outputformat tsv`         | Valores Separados por Tabulação | Copiar dados diretamente para o Excel/Planilhas.         |
| `!outputformat xmlattr`     | Atributos XML                   | Integração de dados baseada em XML.                      |
| `!outputformat xmlelements` | Elementos XML Estruturados      | Geração de arquivos estruturados em tags XML.            |

## 3. Script para Exportação de Dados

| Operação                    | Sequência de Comandos no Terminal                                                                                    |
| :-------------------------- | :------------------------------------------------------------------------------------------------------------------- |
| **Exportar Query para CSV** | ```sql<br>!outputformat csv<br>!record /caminho/data.csv<br>select * from system.catalog limit 10;<br>!record<br>``` |

> 💡 **Nota do Obsidian:** O comando `!record /caminho/arquivo` inicia a gravação do log em arquivo, e o segundo comando `!record` finaliza e fecha o arquivo gerado.

