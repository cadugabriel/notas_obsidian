# 1. O que são Containers?

Ao contrário da virtualização tradicional (como Máquinas Virtuais — VMs), que simula um hardware completo e roda um Sistema Operacional convidado inteiro sobre um Hypervisor, os **Containers** realizam a virtualização a nível de sistema operacional.

Eles isolam os processos da aplicação compartilhando diretamente o **Kernel do sistema hospedeiro (Host)**. Isso os torna extremamente leves, inicializáveis em milissegundos e altamente portáveis entre ambientes de desenvolvimento e produção (como sua estrutura com Python Flask, Gunicorn e Nginx).
