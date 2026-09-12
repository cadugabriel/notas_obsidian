# CONCEITOS

Conceitos relacionados a Inteligência Artificial.

## 1. O que é modelo de linguagem (LLMs) ?

**LLM** = _Large Language Model_ (Modelo de Linguagem de Grande Escala).

São redes neurais treinadas em enormes volumes de texto que aprenderam padrões da linguagem humana. Eles conseguem:
- Entender e gerar texto
- Raciocinar sobre problemas
- Traduzir, resumir, programar, responder perguntas

**Exemplos:** Claude (Anthropic), GPT-4 (OpenAI), Gemini (Google), LLaMA (Meta).

**Como funciona (simplificado):** O modelo recebe um texto de entrada (_prompt_) e prevê, palavra por palavra, qual é a continuação mais provável — mas com bilhões de parâmetros treinados, essa "previsão" se torna raciocínio sofisticado.

  
## 2. O que são agents ?

**Agents** (ou agentes de IA) são sistemas que usam um modelo de linguagem como "cérebro" para **planejar e executar tarefas de forma autônoma**, tomando decisões em múltiplos passos.

Diferente de um chatbot simples que só responde perguntas, um agent pode:
- Usar ferramentas (buscar na web, executar código, ler arquivos)
- Dividir um problema complexo em subtarefas
- Agir em loops: pensar → agir → observar o resultado → pensar novamente

**Analogia:** Um chatbot é como um consultor que responde dúvidas. Um agent é como um funcionário que recebe uma missão e vai até o fim — pesquisa, executa, corrige erros e entrega o resultado.


## 3. O que são SKILL's  de agents ?

**Skills** são módulos de conhecimento ou capacidade que ensinam o agent **como realizar uma tarefa específica**.

Elas funcionam como um "manual de instruções" que o agent lê antes de agir, contendo:
- Quais ferramentas usar
- Qual sequência de passos seguir
- Quais erros evitar
- Boas práticas para aquele domínio

**Exemplo:** Uma skill de "criar arquivo Word" ensina o agent quais bibliotecas instalar, como formatar o documento, onde salvar etc.

**Analogia:** Se o agent é um funcionário, as skills são os **treinamentos e especializações** que ele recebeu — ele consulta o manual antes de começar o trabalho.


## 4. O que é MCP ?

**MCP** significa **Model Context Protocol** — é um protocolo (padrão de comunicação) que permite que modelos de IA se conectem a **ferramentas e serviços externos** de forma padronizada.

Com MCP, um agent pode se conectar a:
- Google Drive, Gmail, Slack
- Bancos de dados
- APIs de terceiros (GitHub, Jira, etc.)
- Ferramentas locais do computador

**Analogia:** O MCP é como uma **tomada universal** — em vez de cada ferramenta ter um plug diferente, o MCP define um formato padrão para que qualquer ferramenta se conecte ao modelo de IA.

### Como tudo se conecta

```
LLM → é o cérebro do → Agent

Agent → usa → Skills (para saber como agir)

Agent → se conecta a ferramentas via → MCP

```

   **LLM** pensa, o **Agent** age, as **Skills** guiam como agir, e o **MCP** conecta o mundo externo.
   