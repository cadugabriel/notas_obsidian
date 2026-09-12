# 🧅 Oracle

Guia de referência para importação massiva de dados usando utilitários Oracle (SQL*Loader) e queries de monitoramento/manutenção de sessões e locks.

---

## 1. Processo de Importação Massiva (SQL Loader)

### Passo 1: Criar Tabela de Destino

```sql
CREATE TABLE ImportFile (
nome VARCHAR2(100),
idade NUMBER(2)
);
```
