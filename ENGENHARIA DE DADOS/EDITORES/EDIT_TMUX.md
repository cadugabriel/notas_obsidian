# 📟 TMUX

Notas do Editor TMUX

---
## Gerenciamento Fora de uma Sessão TMUX

- **Listar conexões:** `tmux ls` (Exibe todas as sessões e janelas ativas em background).

- **Restaurar conexão:** `tmux attach -t "nome_da_conexao"` (Retorna à sessão especificada).

## Atalhos de Controle Interno (Prefixo: `Ctrl + B`)

> 💡 **Nota de Operação:** Pressione `Ctrl + B`, solte as teclas e então digite o caractere ou comando da lista abaixo.

| **Ação Executada**           | **Atalho de Teclado**                             | **Tipo de Controle**              |
| ---------------------------- | ------------------------------------------------- | --------------------------------- |
| **Nova Janela**              | `Ctrl + b` depois `c`                             | Criação de Aba                    |
| **Janela Anterior**          | `Ctrl + b` depois `p`                             | Navegação Global                  |
| **Próxima Janela**           | `Ctrl + b` depois `n`                             | Navegação Global                  |
| **Janela por ID**            | `Ctrl + b` depois `[Número de 0 a 9]`             | Navegação Global                  |
| **Última Janela Ativa**      | `Ctrl + b` depois `l`                             | Navegação Global                  |
| **Renomear Janela**          | `Ctrl + b` depois `,`                             | Organização                       |
| **Listar Janelas**           | `Ctrl + b` depois `w`                             | Organização                       |
| **Dividir Tela Vertical**    | `Ctrl + b` depois `%`                             | Divisão de Painel                 |
| **Dividir Tela Horizontal**  | `Ctrl + b` depois `"`                             | Divisão de Painel                 |
| **Mover Cursor nos Painéis** | `Ctrl + b` depois `Setas Direcionais (← ↓ ↑ →)`   | Navegação Interna                 |
| **Alternar Painéis**         | `Ctrl + b` depois `o`                             | Navegação Interna                 |
| **Redimensionar Painel**     | `Ctrl + b` (Segurando) + `Setas Direcionais`      | Customização de Layout            |
| **Ativar Modo Scroll**       | `Ctrl + b` depois `[` _(Pressione `q` para sair)_ | Leitura de Logs                   |
| **Detachar Sessão**          | `Ctrl + b` depois `d`                             | Sai do TMUX mantendo tudo rodando |
