# Guia de Comandos Markdown

Uma referência rápida e completa de sintaxe Markdown para organizar e formatar suas notas no Obsidian.

---

## 1. Formatação de Texto Básica

| Elemento                | Sintaxe Markdown                      | Resultado Esperado                            |
| :---------------------- | :------------------------------------ | :-------------------------------------------- |
| **Negrito**             | `**Texto em negrito**` ou `__Texto__` | **Texto em negrito**                          |
| *Itálico*               | `*Texto em itálico*` ou `_Texto_`     | *Texto em itálico*                            |
| ***Negrito e Itálico*** | `***Texto combinado***`               | ***Texto combinado***                         |
| ~~Tachado~~             | `~~Texto riscado~~`                   | ~~Texto riscado~~                             |
| ==Marcador / Realce==   | `==Texto destacado==`                 | ==Texto destacado== *(Suportado no Obsidian)* |
| Sublinhado              | `<u>Texto sublinhado</u>`             | <u>Texto sublinhado</u> *(HTML)*              |
| Expoente                | `Texto^superior^` ou `X²`             | X² ou Texto<sup>superior</sup>                |
| Subscrito               | `Texto~inferior~` ou `H₂O`            | H₂O ou Texto<sub>inferior</sub>               |
 
---

## 2. Títulos e Cabeçalhos

| Elemento        | Sintaxe Markdown       | Nível de Importância |
| :-------------- | :--------------------- | :------------------- |
| # Título 1      | `# Título Principal`   | Principal (H1)       |
| ## Título 2     | `## Seção Principal`   | Seção (H2)           |
| ### Título 3    | `### Subseção`         | Subseção (H3)        |
| #### Título 4   | `#### Tópico Interno`  | Detalhe (H4)         |
| ##### Título 5  | `##### Subtópico`      | Detalhe menor (H5)   |
| ###### Título 6 | `###### Título Mínimo` | Tamanho mínimo (H6)  |

---

## 3. Listas e Organização

  
| Tipo de Lista                    | Sintaxe Markdown                                    | Exemplo Prático                         |
| :------------------------------- | :-------------------------------------------------- | :-------------------------------------- |
| **Não ordenada**                 | `- Item 1`<br>`* Item 2`<br>`+ Item 3`              | • Item 1<br>• Item 2 <br>• Item 3       |
| **Ordenada**                     | `1. Primeiro`<br>`2. Segundo`                       | 1. Primeiro<br>2. Segundo               |
| **Lista de Tarefas (Checklist)** | `- [ ] Tarefa pendente`<br>`- [x] Tarefa concluída` | ☐ Tarefa pendente<br>☑ Tarefa concluída |
| **Listas Alinhadas (Recuo)**     | ` - Subitem (4 espaços ou Tab)`                     | Bloqueia recuo interno na lista         |

---

## 4. Blocos de Código, Citações e Links

| Elemento                 | Sintaxe Markdown                         | Resultado / Uso                               |
| :----------------------- | :--------------------------------------- | :-------------------------------------------- |
| **Código em Linha**      | `` `código aqui` ``                      | `Destaca comandos ou variáveis no texto`      |
| **Bloco de Código**      | \`\`\`python<br>print("Olá")<br>\`\`\`   | Bloco formatado com sintaxe da linguagem      |
| **Citação (Blockquote)** | `> Este é um bloco de citação.`          | Recua o texto com uma barra vertical lateral  |
| **Link Externo**         | `[Nome do Site](https://url.com)`        | [Nome do Site](https://url.com)               |
| **Link Interno (Wiki)**  | `[[Nome da Nota]]`                       | Cria conexões entre notas *(Padrão Obsidian)* |
| **Âncora de Cabeçalho**  | `[[Nome da Nota#Título 2]]`              | Direciona o link para um título específico    |
| **Exibir Imagem**        | `![Legenda](https://url.com/imagem.png)` | Renderiza a imagem diretamente na nota        |

---

## 5. Elementos Avançados e Tabelas

| Elemento                       | Sintaxe Markdown                                                                  | Notas de Implementação                                              |
| :----------------------------- | :-------------------------------------------------------------------------------- | :------------------------------------------------------------------ |
| **Linha Divisória**            | `---` ou `***` ou `___`                                                           | Cria uma linha horizontal de separação                              |
| **Item Esquerda                | :---                                                                              |                                                                     |
| **Item Centro                  | :---:                                                                             |                                                                     |
| **Item Direita                 | \---:                                                                             |                                                                     |
| **Quebra de Linha Forçada**    | `Duas soluções:`<br>Insira dois espaços ao final da linha <br>ou use a tag `<br>` | Força o texto a ir para a próxima linha sem criar um novo parágrafo |
| **Ocultar Comentários**        | `%% Este comentário fica invisível %%`                                            | Útil para anotações pessoais ocultas *(Obsidian)*                   |
| **Bloco Colapsável (Spoiler)** | `<details><summary>Clique aqui</summary>Conteúdo oculto</details>`                | Cria menus expansíveis e retráteis nativos                          |
| **Notas de Rodapé**            | `Texto principal[^1]` <br><br> `[^1]: Detalhe no rodapé.`                         | Cria referências numeradas automaticamente ao final do documento    |
| **Equações Matemáticas**       | `$E = mc^2$` (Linha)<br>`$$ \sum_{i=1}^n i = \frac{n(n+1)}{2} $$` (Bloco)         | Renderiza fórmulas matemáticas usando sintaxe LaTeX (MathJax)       |
