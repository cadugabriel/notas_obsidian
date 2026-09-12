# 🐧 Linux

Guia central de comandos para administração de sistemas, gerenciamento de recursos com Hadoop YARN/HDFS, controle de terminais via TMUX e automação de agendamentos no Cron.

---

## 1. Comandos Gerais de Sistema, Rede e WSL

### Monitoramento de Processos e Pacotes

| Função                 | Comando Linux                       | Descrição                                                            |
| :--------------------- | :---------------------------------- | :------------------------------------------------------------------- |
| **Cópia de Arquivos**  | `scp ORIGEM DESTINO`                | Copia arquivos de forma segura entre servidores Linux diferentes.    |
| **Listar Portas**      | `sudo lsof -i -P -n \| grep LISTEN` | Lista processos e serviços escutando conexões de rede locais.        |
| **Derrubar Porta TCP** | `sudo fuser -k <porta>/tcp`         | Mata forçadamente o processo que está usando uma porta de rede.      |
| **Listar Disponíveis** | `sudo apt list`                     | Exibe todos os pacotes disponíveis no repositório oficial da distro. |
| **Listar Instalados**  | `sudo apt list --installed`         | Lista apenas os pacotes de software instalados no sistema atual.     |
