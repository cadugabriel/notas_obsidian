# WSDL

Notas gerais relacionadas a comandos LINUX dentro do Windows através do WSDL.

---

## Alterar Senha do Root no WSL (Windows Subsystem for Linux)

1. Abra o **PowerShell** no Windows como **Administrador**.

2. Altere o usuário padrão temporariamente para root executando:

```Shell
ubuntu config --default-user root
```

  
- Inicie sua distribuição Linux normalmente pelo terminal.
- Dentro do ambiente Linux logado como root, execute o comando de redefinição de senha:

```Bash
passwd roo
```