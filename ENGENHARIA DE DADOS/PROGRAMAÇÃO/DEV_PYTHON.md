# OBJETIVO

Guia de referencia sobre assuntos relacionados a python, pySpark e pyTests.

---

## AMBIENTES VIRTUAIS

O uso de ambientes virtuais isola as bibliotecas do seu projeto do Python global do sistema operacional, evitando conflitos de versões.

| Operação               | Comando Linux / macOS       | Comando Windows (PowerShell) |
| :--------------------- | :-------------------------- | :--------------------------- |
| **1. Criar Ambiente**  | `python3 -m venv .venv`     | `python -m venv .venv`       |
| **2. Ativar Ambiente** | `source .venv/bin/activate` | `.venv\Scripts\Activate.ps1` |
| **3. Desativar**       | `deactivate`                | `deactivate`                 |

---

## Gerenciamento de Pacotes (`pip`)

Comandos essenciais para instalar, atualizar e listar as dependências dentro do ambiente virtual ativo.

### Comandos Rápidos de Instalação e Limpeza
```bash
# Instalar um pacote específico (ex: Flask)
pip install flask


# Instalar uma versão exata de um pacote
pip install flask==3.0.0

  
# Atualizar um pacote para a última versão estável
pip install --upgrade flask

# Desinstalar um pacote do ambiente corrente
pip uninstall flask
```

---
## Controle e Reprodução de Ambientes

| **Objetivo** | **Comando Executável** | **Descrição** |
| -------------------------- | --------------------------------- | ---------------------------------------------------------------------------------------------- |
| **Exportar Dependências** | `pip freeze > requirements.txt` | Salva todos os pacotes instalados e suas versões exatas em um arquivo de texto. |
| **Instalar de um Arquivo** | `pip install -r requirements.txt` | Lê o arquivo gerado e instala todas as dependências em lote no novo ambiente. |
| **Listar Pacotes** | `pip list` | Exibe uma tabela simples no terminal com as bibliotecas instaladas e suas respectivas versões. |

---

## SMALL CODE

### ty..catch:
```python
# noinspection PyBroadException
try:
...
exception:
...
```

---

## DICAS

### Transformar método em estático

```python
@staticmethod
```


### PYTEST

``` python
# Método 1
pytest

# Método 2
pytest -vv

# Método 3
pytest [-vv] [caminho da pasta ou do arquivo]
```


### COMPILAR PACOTES .WHL

```python
# Limpar arquivos temporários
python setup.py clean --all

# Cria binários Wheel
- python setup.py bdist_wheel	:  (se tiver arquivo .toml ai seria python -m build) 
```

