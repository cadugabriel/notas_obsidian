# OBJETIVO

Guia de referência sobre assuntos relacionados a GIT, GIT HUB e versionamento de códigos ou conteúdos.

---

## 01-CONCEITOS GERAIS

> [!ABSTRACT] Definição Simples O **Rebase** move seus commits para o **início da fila**. Ele reescreve o histórico para parecer que você começou a trabalhar **depois** das últimas atualizações, evitando cruzamentos.

  
> [!IMPORTANT] Regra de Ouro **Rebase = Reorganizar a história.** Cria um histórico **linear e limpo**. ⚠️ **NUNCA** use em branches públicas ou compartilhadas (reescrita de história causa conflitos para outros).

  
> [!TIP] Merge vs. Rebase
> - **Merge:** "Juntou nosso trabalho" (cria um commit de união/cruzamento).
> - **Rebase:** "Fingiu que meu trabalho foi feito depois do seu" (histórico reto).

---

## 02-COMANDOS GIT ESSENCIAIS

| **Comando**                     | **Descrição**                                                                                                          |
| :------------------------------ | :--------------------------------------------------------------------------------------------------------------------- |
| `git clone "URL"`               | Baixa o repositório.                                                                                                   |
| `git clone "URL" alias`         | Baixa o repositório com outro nome de pasta.                                                                           |
| `git branch`                    | Mostra a branch atual.                                                                                                 |
| `git branch -a`                 | Lista todas as branches (locais e remotas).                                                                            |
| `git branch -v`                 | Mostra o último commit de cada branch local.                                                                           |
| `git branch -d "nome"`          | Remove branch local (seguro, só se já foi mergeada).                                                                   |
| `git branch -D "nome"`          | Força a exclusão da branch local.                                                                                      |
| `git checkout "nome"`           | Muda para outra branch. Se usar no final por exemplo "origin/develop" siginifica que a origem é a develop do servidor. |
| `git checkout -b "nome"`        | Cria e muda para uma nova branch.                                                                                      |
| `git checkout -t "origem"`      | Cria branch local baseada em uma remota.                                                                               |
| `git status`                    | Mostra o estado da sincronia (arquivos modificados/staged).                                                            |
| `git add .`                     | Adiciona todas as alterações locais para o stage.                                                                      |
| `git commit -m "msg"`           | Salva as alterações localmente com uma mensagem.                                                                       |
| `git push`                      | Envia os commits locais para o servidor.                                                                               |
| `git push -u origin <branch>`   | Envia e vincula a branch local à remota (primeira vez).                                                                |
| `git fetch`                     | Baixa atualizações do servidor sem mesclar (seguro).                                                                   |
| `git fetch origin`              | Atualiza referências da branch original.                                                                               |
| `git pull`                      | Baixa e mescla (`fetch` + `merge`) atualizações do servidor.                                                           |
| `git pull origin develop`       | Traz a branch `develop` para a sua branch atual.                                                                       |
| `git merge "branch"`            | Une o histórico de outra branch à atual (pode gerar conflitos).                                                        |
| `git stash`                     | Guarda alterações temporárias na "pilha" para trocar de branch.                                                        |
| `git config --list`             | Lista todas as configurações do Git. <br>--list pode ser local ou global                                               |
| `git config user.name "Nome"`   | Define o nome do usuário (use `--global` para todos os projetos).                                                      |
| `git config user.email "email"` | Define o e-mail do usuário (use `--global` para todos).                                                                |
| `git subtree add -P`            | Integra outro repositório como subdiretório.                                                                           |

---

## 03-COMO ATUALIZAR BRANCH LOCAL

Forma 1 - Atualiza o DEVELOP local e depois a branch local:
```bash
## 1. Vá para a develop local
git checkout develop

  
## 2. Baixe as alterações do remoto
git fetch origin


## 3. Atualize sua develop local
git pull origin develop


## 4. Volte para sua branch
git checkout sua-branch

  
## 5. Traga a develop atualizada para sua branch
git merge develop
```

Forma 2 - Atualizar a branch local sem atualizar a develop local:
```bash
git fetch origin
git checkout sua-branch
git merge origin/develop
```

  
Forma 3 - Atualizar a branch local com **REBASE** sem atualizar a develop local:
```bash
git fetch origin
git checkout sua-branch
git rebase origin/develop


# Após resolver conflitos, adicinar alterações
git add .
git rebase --continue

  
# Se quiser desistir
git rebase --abort
```

---

## 04-GIT CLONE MULTIMPLAS CONTAS
```bash
git clone git@github-pessoal:cadugabriel/<repos.git>
git clone git@github-sensedia:carlosergabriel/<repos.git>
```

---
## 99-OUTRAS DICAS

### 1. Como saber quantos commits a develop avançou

```bash
git fetch origin
git log --oneline HEAD..origin/develop
```

### 2. Como saber quantos commits a develop avançou (quantidade)

```bash
git fetch origin
git rev-list --count HEAD..origin/develop
```

