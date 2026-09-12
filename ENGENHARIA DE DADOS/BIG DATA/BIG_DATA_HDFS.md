# HSFS

Notas relacionas ao HDFS do ecossistema BIG DATA

---
## Manipulação de Arquivos no HDFS

```
# Listar o conteúdo de um diretório ou arquivo no HDFS
hdfs dfs -ls "caminho"

# Excluir um arquivo ignorando a lixeira (Remoção permanente)
hdfs dfs -rm -skipTrash "caminho"

# Copiar arquivo do HDFS para o ambiente local (Download)
hdfs dfs -get ORIGEM DESTINO

# Copiar arquivo do ambiente local para o cluster HDFS (Upload)
hdfs dfs -put ORIGEM DESTINO
```
