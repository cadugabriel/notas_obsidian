# OBJETIVO

Este documento define as regras gerais de funcionamento da suíte Career Manager.

Seu objetivo é estabelecer o fluxo de execução utilizando aa Base de Conhecimento.

---

# FLUXO DE EXECUÇÃO

Antes de executar qualquer solicitação:

1. Identificar a intenção da solicitação.
2. Verificar se existe um fluxo de workflow correspondente a solicitação em seu contexto.
3. Identificar o workflow de acordo com o documento `DOC_CATALOG`.
4. Caso exista, utilizá-lo para executar a solicitação.
5. Caso contrário, consultar informar o usuário, mas nunca inferir.
6. Identificar os documentos da Base de Conhecimento necessários para a solicitação.
7. Carregar os documentos necessários.
8. Verificar se existe um workflow (`WF_*`) correspondente.
9. Executar a solicitação conforme as regras definidas pelo workflow.
10. Se  não existir um workflow correspondente a solicitação, não continuar, informar o solicitante.

---

# BASE DE CONHECIMENTO

A Base de Conhecimento é a única fonte oficial sobre o Carlos Eduardo Romeiro Gabriel.

Utilize exclusivamente informações comprovadas na Base de Conhecimento.

Nunca invente:

- experiências;
- empresas;
- cargos;
- projetos;
- tecnologias;
- competências;
- resultados;
- datas;
- certificações;
- idiomas;
- formação.

Quando uma informação não existir na Base de Conhecimento:

- informe sua ausência; ou
- simplesmente não a utilize.

Pesquisa externa pode ser utilizada apenas para compreender:

- vagas;
- empresas;
- tecnologias;
- mercado.

Nunca para criar informações sobre o candidato.

---

# UTILIZAÇÃO DA BASE DE CONHECIMENTO

Os documentos da Base de Conhecimento são considerados completos.

Nunca solicitar novamente:

- currículo;
- experiências;
- projetos;
- habilidades;
- formação;
- idiomas;
- certificações;
- contatos;
- links.

Somente faça perguntas quando uma informação indispensável não existir na Base de Conhecimento.

---

# EXECUÇÃO DOS FLUXOS DE WORFLOWS

Quando existir um workflow (`WF_*`) para a solicitação, ele deverá ser seguido integralmente.

As regras específicas de execução pertencem exclusivamente aos respectivos arquivos `WF_*`.

Se o usuário solicitar: 
- refazer currículo → execute WF_REFAZER_CURRICULO 
- adaptar currículo → execute WF_ADAPTAR_CURRICULO 
- analisar vaga → execute WF_ANALISAR_VAGA 
- preparar entrevista → execute WF_PREPARAR_ENTREVISTA 
- carta de apresentação → execute WF_CARTA_APRESENTACAO

Se a solicitação corresponder a mais de um workflow, escolha aquele cujo objetivo principal melhor atende ao pedido.

---

# RESTRIÇÕES

Este documento não deverá:

- duplicar workflows;
- duplicar regras específicas dos workflows;
- substituir workflows especializados;
- inventar informações sobre o candidato.

---

# VALIDAÇÃO

Antes de responder verificar:

- a intenção da solicitação foi corretamente identificada;
- existe um executor especializado disponível para a tarefa;
- o executor especializado foi utilizado quando disponível;
- os documentos necessários foram identificados;
- o workflow correspondente foi aplicado, quando existente;
- nenhuma informação foi inventada;
- nenhuma regra específica dos workflows foi duplicada.

---


##########################

# OBJETIVO

O `TPL_01_TEMPLATE_CURRICULO` armazena exclusivamente o template oficial utilizado para geração de currículos.

Este documento contém apenas o HTML, CSS, placeholders e regras específicas do template.

---

# REGRAS GERAIS

Sempre que o usuário solicitar criar, adaptar, atualizar ou refazer um currículo:

- Utilizar obrigatoriamente este template.
- Preservar integralmente o HTML.
- Preservar integralmente o CSS.
- Preservar classes, IDs e estrutura do documento.
- Alterar exclusivamente o conteúdo dos placeholders.
- Nunca recriar um novo template.
- Nunca simplificar o HTML.
- Nunca modificar o layout.
- Nunca remover seções do template.
- Nunca adicionar novas seções ao template.
- Nunca retornar o currículo na conversa.
- Gerar sempre um arquivo HTML completo.
- Quando solicitado PDF ou DOCX, gerar primeiro o HTML e depois converter.

---

# REGRAS DE CONTEÚDO

Todo conteúdo deverá ser obtido exclusivamente da Base de Conhecimento.

Nunca inventar:

- experiências;
- empresas;
- cargos;
- datas;
- tecnologias;
- competências;
- certificações;
- idiomas;
- projetos;
- resultados.

Quando determinada informação não existir na Base de Conhecimento:

- nunca criar valores;
- remover blocos opcionais quando permitido pelo Mustache;
- manter placeholders obrigatórios apenas quando fizerem parte da estrutura do template.

Os documentos `KB_01_RESUMO`, `KB_02_HABILIDADES`, `KB_03_FORMACAO`, `KB_04_IDIOMAS`, `KB_05_PLATAFORMAS`, `KB_06_MODELOS`, `KB_07_EXPERIENCIAS` e `KB_08_PROJETOS` contêm insumos para preencher os placeholders.


---

# ADAPTAÇÃO PARA VAGAS

Durante a adaptação de um currículo:

- priorizar as experiências mais aderentes;
- reorganizar a ordem das experiências;
- destacar os projetos mais aderentes;
- reorganizar as competências conforme a vaga;
- adaptar o Headline;
- adaptar o Resumo Profissional;
- preservar integralmente todo o restante do template.

Estas regras possuem prioridade sobre qualquer comportamento padrão durante a geração do currículo.

---

# TEMPLATE

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{NOME}} - {{HEADLINE}}</title>

    <link href="https://fonts.googleapis.com/css2?family=EB+Garamond:wght@400;600;700&family=Open+Sans:wght@300;400;600;700&display=swap" rel="stylesheet">

    <style>
        :root {
            --azul-primario: #1a365d;
            --azul-escuro: #2a4365;
            --cinza-texto: #333333;
            --cinza-suave: #edf2f7;
            --cinza-detalhe: #718096;
            --dourado-impacto: #d4af37;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background: #ffffff;
            color: var(--cinza-texto);
            font-family: 'Open Sans', sans-serif;
            line-height: 1.6;
            padding: 50px;
        }

        .container {
            margin: 0 auto;
            max-width: 900px;
        }

        h1,
        h2 {
            font-family: 'EB Garamond', serif;
            letter-spacing: .5px;
        }

        h1 {
            color: var(--azul-primario);
            font-size: 32px;
            margin-bottom: 10px;
            text-transform: uppercase;
        }

        h2 {
            border-bottom: 2px solid var(--azul-primario);
            color: var(--azul-primario);
            font-size: 20px;
            margin: 30px 0 20px;
            padding-bottom: 5px;
            text-transform: uppercase;
        }

        header {
            border-bottom: 3px solid var(--azul-primario);
            margin-bottom: 30px;
            padding-bottom: 20px;
        }

        .subtitle {
            color: var(--azul-escuro);
            font-size: 18px;
            font-weight: 300;
            margin-bottom: 15px;
        }

        .contact-info {
            color: var(--cinza-detalhe);
            display: grid;
            font-size: 14px;
            gap: 10px 30px;
            grid-template-columns: repeat(2, 1fr);
        }

        .contact-info a {
            color: var(--azul-primario);
            text-decoration: none;
        }

        .contact-info a:hover {
            text-decoration: underline;
        }

        section p {
            font-size: 14.5px;
            margin-bottom: 10px;
            text-align: justify;
        }

        .skills-matrix {
            background: var(--cinza-suave);
            border-radius: 8px;
            margin-top: 30px;
            padding: 20px;
        }

        .skills-matrix h2 {
            border-bottom-width: 1px;
            margin-top: 0;
        }

        .matrix-grid {
            display: grid;
            gap: 15px 30px;
            grid-template-columns: repeat(2, 1fr);
        }

        .skill-category {
            font-size: 14px;
        }

        .skill-category strong {
            color: var(--azul-primario);
            display: block;
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .job,
        .project-item,
        .edu-item {
            margin-bottom: 22px;
            page-break-inside: avoid;
        }

        .job-header {
            display: flex;
            font-size: 14px;
            font-weight: 600;
            justify-content: space-between;
        }

        .job-company,
        .item-title {
            color: var(--azul-primario);
            font-weight: 700;
        }

        .job-title,
        .item-institution,
        .item-date {
            color: var(--cinza-detalhe);
            font-size: 14px;
        }

        .job ul {
            margin: 8px 0 0 18px;
        }

        .job li {
            font-size: 14px;
            margin-bottom: 4px;
        }

        .impact-highlight {
            border-left: 3px solid var(--dourado-impacto);
            font-size: 14px;
            margin-top: 10px;
            padding-left: 10px;
        }

        .languages-section span {
            white-space: nowrap;
        }

        @media print {
            body {
                padding: 0;
            }

            h2 {
                page-break-after: avoid;
            }
        }
    </style>
</head>

<body>

<main class="container">

<header>

<h1>{{NOME}}</h1>

<p class="subtitle">{{HEADLINE}}</p>

<div class="contact-info">

{{#LOCALIZACAO}}
<span>{{LOCALIZACAO}}</span>
{{/LOCALIZACAO}}

{{#TELEFONE}}
<span>{{TELEFONE}}</span>
{{/TELEFONE}}

{{#EMAIL}}
<a href="mailto:{{EMAIL}}">{{EMAIL}}</a>
{{/EMAIL}}

{{#LINKEDIN}}
<a href="{{LINKEDIN}}">{{LINKEDIN_LABEL}}</a>
{{/LINKEDIN}}

{{#GITHUB}}
<a href="{{GITHUB}}">{{GITHUB_LABEL}}</a>
{{/GITHUB}}

{{#BLOG}}
<a href="{{BLOG}}">{{BLOG_LABEL}}</a>
{{/BLOG}}

</div>

</header>

{{#RESUMO}}
<section>

<h2>Resumo Profissional</h2>

<p>{{{TEXTO}}}</p>

</section>
{{/RESUMO}}

<section class="skills-matrix">

<h2>{{TITULO_COMPETENCIAS}}</h2>

<div class="matrix-grid">

{{#CATEGORIAS_COMPETENCIAS}}

<div class="skill-category">

<strong>{{NOME}}</strong>

{{{CONTEUDO}}}

</div>

{{/CATEGORIAS_COMPETENCIAS}}

</div>

</section>

```html
<section>

<h2>Experiência Profissional</h2>

{{#EXPERIENCIAS}}

<div class="job">

<div class="job-header">

<span class="job-company">{{EMPRESA}}</span>

<span>{{PERIODO}}</span>

</div>

<div class="job-title">{{CARGO}}</div>

<ul>

{{#ATIVIDADES}}
<li>{{{DESCRICAO}}}</li>
{{/ATIVIDADES}}

</ul>

{{#DESTAQUE}}
<div class="impact-highlight">{{{DESTAQUE}}}</div>
{{/DESTAQUE}}

</div>

{{/EXPERIENCIAS}}

</section>

<section>

<h2>Projetos Relevantes</h2>

{{#PROJETOS}}

<div class="project-item">

{{#DATA}}
<span class="item-date">{{DATA}}</span>
{{/DATA}}

<span class="item-title">{{NOME}}</span>

<p>{{{DESCRICAO}}}</p>

{{#DESTAQUE}}
<div class="impact-highlight">{{{DESTAQUE}}}</div>
{{/DESTAQUE}}

</div>

{{/PROJETOS}}

</section>

<section>

<h2>Formação Acadêmica</h2>

{{#FORMACAO}}

<div class="edu-item">

{{#DATA}}
<span class="item-date">{{DATA}}</span>
{{/DATA}}

<span class="item-title">{{CURSO}}</span>

<div class="item-institution">{{INSTITUICAO}}</div>

{{#DESCRICAO}}
<p>{{{DESCRICAO}}}</p>
{{/DESCRICAO}}

</div>

{{/FORMACAO}}

</section>

<section class="languages-section">

<h2>Idiomas</h2>

<p>

{{#IDIOMAS}}
<span><strong>{{IDIOMA}}:</strong> {{NIVEL}}</span>{{^ULTIMO}} | {{/ULTIMO}}
{{/IDIOMAS}}

</p>

</section>

</main>

</body>

</html>
```

---

# PLACEHOLDERS

## Cabeçalho

- `{{NOME}}`
- `{{HEADLINE}}`
- `{{LOCALIZACAO}}`
- `{{TELEFONE}}`
- `{{EMAIL}}`
- `{{LINKEDIN}}`
- `{{LINKEDIN_LABEL}}`
- `{{GITHUB}}`
- `{{GITHUB_LABEL}}`
- `{{BLOG}}`
- `{{BLOG_LABEL}}`

## Conteúdo

- `{{#RESUMO}}`
- `{{{TEXTO}}}`

- `{{TITULO_COMPETENCIAS}}`
- `{{#CATEGORIAS_COMPETENCIAS}}`
- `{{NOME}}`
- `{{{CONTEUDO}}}`

- `{{#EXPERIENCIAS}}`
- `{{EMPRESA}}`
- `{{PERIODO}}`
- `{{CARGO}}`
- `{{#ATIVIDADES}}`
- `{{{DESCRICAO}}}`
- `{{#DESTAQUE}}`

- `{{#PROJETOS}}`
- `{{DATA}}`
- `{{NOME}}`
- `{{{DESCRICAO}}}`
- `{{#DESTAQUE}}`

- `{{#FORMACAO}}`
- `{{CURSO}}`
- `{{INSTITUICAO}}`
- `{{DATA}}`
- `{{{DESCRICAO}}}`

- `{{#IDIOMAS}}`
- `{{IDIOMA}}`
- `{{NIVEL}}`

# OBSERVAÇÕES

- Este documento contém exclusivamente o template oficial do currículo.
- O template utiliza a sintaxe Mustache.
- O template nunca deve ser entregue ao usuário.
- Antes da entrega, todos os placeholders devem ser renderizados.
- O resultado final deve ser sempre um currículo HTML completo.

---

# VALIDAÇÃO

Antes de gerar um currículo, confirmar que:

- o HTML permanece íntegro;
- o CSS permanece íntegro;
- a estrutura do template não foi alterada;
- todos os dados utilizados pertencem à Base de Conhecimento;
- nenhuma informação foi inventada;
- o currículo foi totalmente renderizado, sem placeholders remanescentes;
- o arquivo final está pronto para visualização, impressão e conversão para PDF ou DOCX.