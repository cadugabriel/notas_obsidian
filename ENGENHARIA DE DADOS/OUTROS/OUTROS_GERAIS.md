# INSTRUÇÃO

Notas gerais sobre diversos assuntos.

---

## CONCEITOS GERAIS

| CONCEITO     | DESCRIÇÃO                                                                                                                                                |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `TL;DR`      | abreviação da expressão em inglês "Too Long; Didn't Read", que em português significa "Muito longo; não li".                                             |
| `Throughput` | Taxa real de transferencia de dados                                                                                                                      |
| `Amazon SQS` | Serviço de filas                                                                                                                                         |
| `RU`         | É a “moeda” abstrata do Azure Cosmos DB: cada operação (read/write/query/transaction) consome RUs; RU/s é a taxa de throughput provisionado por segundo. |
|              |                                                                                                                                                          |

## DDA e DDI

| Aspecto                 | DDA (Data-Driven Architecture) | DDI (Data-Driven Integration)     |
| ----------------------- | ------------------------------ | --------------------------------- |
| **Foco**                | Estrutura e desenho do sistema | Conexão entre sistemas e dados    |
| **Objetivo principal**  | Escalabilidade e governança    | Interoperabilidade e consistência |
| **Ferramentas típicas** | Data lakes, DW, pipelines      | ETL/ELT, APIs, conectores         |
| **Benefício**           | Melhor tomada de decisão       | Visão unificada dos dados         |

## Data Lake X Data Mesh

| Aspecto                 | Data Lake                            | Data Mesh                            |
| ----------------------- | ------------------------------------ | ------------------------------------ |
| **Foco**                | Centralização de dados               | Descentralização por domínios        |
| **Armazenamento**       | Dados brutos em um único repositório | Dados tratados como produtos         |
| **Governança**          | Centralizada                         | Distribuída entre equipes            |
| **Escalabilidade**      | Técnica (infraestrutura)             | Organizacional (processos e cultura) |
| **Benefício principal** | Flexibilidade e volume               | Qualidade e autonomia dos domínios   |
| **Risco**               | Virar “data swamp”                   | Complexidade de coordenação          |

## ADOM:
- Definição: Administrative Domain — uma instância lógica dentro do FortiManager usada para gerenciar dispositivos FortiGate.
- Função: Permite separar ambientes de administração (ex.: produção, testes, clientes diferentes).
- API: O FortiManager expõe endpoints para criar, listar e gerenciar ADOMs.
