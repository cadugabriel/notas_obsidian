# 🪟 Windows

Procedimento técnico para desinstalação e reinstalação do navegador nativo utilizando o Gerenciador de Pacotes do Windows (Winget).

---

## 1. Comportamento do Sistema

> ℹ️ **Nota de Armazenamento:** É possível desinstalar o Microsoft Edge do sistema. No entanto, ele continuará sendo exibido na listagem oficial de aplicativos do Windows, passando a ocupar apenas **46 KB** de espaço em disco após o procedimento.

---

## 2. Procedimentos via PowerShell (Administrador)

| Operação               | Sequência de Passos                                                                                                          | Comando Executável                                      |
| :--------------------- | :--------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------ |
| **Desinstalar o Edge** | 1. Pressione `Win + X`. <br>2. Abra o **Windows PowerShell (Admin)**. <br>3. Insira o comando ao lado e aguarde a conclusão. | ```powershell<br>winget uninstall Microsoft.Edge<br>``` |
| **Reinstalar o Edge**  | 1. Pressione `Win + X`. <br>2. Abra o **Windows PowerShell (Admin)**. <br>3. Insira o comando ao lado e aguarde a conclusão. | ```powershell<br>winget install Microsoft.Edge<br>```   |
