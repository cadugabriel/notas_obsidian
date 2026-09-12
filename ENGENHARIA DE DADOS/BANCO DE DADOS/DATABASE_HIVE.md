# 🐝 Apache Hive

Guia rápido de referência para administração de schemas, exportação via Beeline e DDL (Data Definition Language) no Hive.

---
## 1. Comandos Básicos (CLI / Beeline)

| Função                | Comando Hive / Configuração       | Descrição                                                        |
| :-------------------- | :-------------------------------- | :--------------------------------------------------------------- |
| **Listar Schemas**    | `show databases;`                 | Lista todos os bancos de dados/schemas disponíveis.              |
| **Selecionar Schema** | `use "nome_schema";`              | Altera o contexto atual para o schema especificado.              |
| **Listar Tabelas**    | `show tables;`                    | Lista todas as tabelas dentro do schema selecionado.             |
| **Exibir Cabeçalho**  | `set hive.cli.print.header=true;` | Ativa a exibição do nome das colunas nos resultados das queries. |

## 2. Exportação de Dados via Terminal

| Operação              | Script de Exportação                                                                                                                                                                    |
| :-------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Exportar para CSV** | ```bash<br>beeline -u "jdbc:hive2://conexao" \<br> --showHeader=false \<br> --verbose=false \<br> --outputformat=csv2 -e "select * from system.catalog limit 10" > /tmp/data.txt<br>``` |

## 3. Estrutura de Criação de Tabela (DDL)

```sql

-- Remove a tabela caso ela já exista no schema

DROP TABLE IF EXISTS DB_DOLPHIN_TARGET.NOME_TABELA;

  
-- Criação de tabela externa definindo tipos e armazenamento

CREATE EXTERNAL TABLE DB_DOLPHIN_TARGET.NOME_TABELA (

CAMPO01 STRING,

CAMPO02 STRING,

CAMPO03 STRING

)

STORED AS PARQUET

LOCATION 'CAMINHO DO HDFS';

# SEO

#database #bancodedados #hive #phoenix

```