# Objetivo

Centralizar todas as características técnicas das mídias sociais.

Este documento descreve apenas capacidades, formatos e recursos disponíveis em cada plataforma.

Não define estratégias de conteúdo.

Não define SEO.

Não define Copywriting.

Não define Workflows.

---

# Responsabilidades

Este documento é responsável por definir:

- plataformas suportadas;
- formatos aceitos;
- recursos disponíveis;
- limitações técnicas;
- compatibilidade entre plataformas e tipos de conteúdo.

---

# Não é responsabilidade

Este documento nunca deverá conter:

- SEO;
- Copywriting;
- Workflows;
- regras dos Projetos;
- identidade visual;
- tom de voz;
- estratégias de engajamento.

---

# Estrutura

Toda plataforma deverá seguir a estrutura abaixo.

```yaml
Plataforma:

Conteúdos:

Formatos:

Recursos:

Limitações:
```

---

# Plataformas

## YouTube

```yaml
Plataforma:
  YouTube

Conteúdos:
  - Vídeo
  - Short
  - Live
  - Comunidade

Formatos:
  - Horizontal
  - Vertical

Recursos:
  - Thumbnail
  - Playlist
  - Cards
  - Música    
  - Tela Final
  - Capítulos
  - Legendas
  - Descrição
  - Comentário Fixado

Limitações:
  Nenhuma relevante para esta arquitetura.
```

---

## TikTok

```yaml
Plataforma:
  TikTok

Conteúdos:
  - Short

Formatos:
  - Vertical

Recursos:
  - Legendas
  - Hashtags
  - Capa

Limitações:
  Não suporta artigos.
```

---

## Instagram

```yaml
Plataforma:
  Instagram

Conteúdos:
  - Reel
  - Feed
  - Story
  - Carrossel

Formatos:
  - Vertical
  - Quadrado

Recursos:
  - Música
  - Stories
  - Destaques
  - Colaboração

Limitações:
  Não suporta artigos completos.
```

---

## Facebook

```yaml
Plataforma:
  Facebook

Conteúdos:
  - Vídeo
  - Reel
  - Post
  - Foto

Formatos:
  - Horizontal
  - Vertical

Recursos:
  - Comentários
  - Compartilhamentos
  - Descrição

Limitações:
  Não suporta artigos completos.
```

---

## LinkedIn

```yaml
Plataforma:
  LinkedIn

Conteúdos:
  - Post
  - Artigo
  - Documento
  - Imagem

Formatos:
  - Texto
  - Documento
  - Imagem

Recursos:
  - Artigos
  - Newsletter
  - Comentários

Limitações:
  Não suporta vídeos curtos como formato principal.
```

---

## Blog

```yaml
Plataforma:
  Blog

Conteúdos:
  - Artigo
  - Tutorial
  - Guia
  - Notícia

Formatos:
  - Texto

Recursos:
  - SEO
  - Categorias
  - Tags
  - Links internos
  - Imagens

Limitações:
  Não suporta vídeos nativamente.
```

---

## X

```yaml
Plataforma:
  X

Conteúdos:
  - Post
  - Imagem
  - Vídeo
  - Thread

Formatos:
  - Texto
  - Vertical
  - Horizontal

Recursos:
  - Hashtags
  - Threads
  - Mídia

Limitações:
  Conteúdo textual limitado.
```

---

# Compatibilidade

| Plataforma | Vídeo | Short | Artigo |    Post    | Story | Carrossel |
| ---------- | :---: | :---: | :----: | :--------: | :---: | :-------: |
| YouTube    |   ✅   |   ✅   |   ❌    | Comunidade |   ❌   |     ❌     |
| TikTok     |   ❌   |   ✅   |   ❌    |     ✅      |   ❌   |     ❌     |
| Instagram  |   ❌   |   ✅   |   ❌    |     ✅      |   ✅   |     ✅     |
| Facebook   |   ❌   |   ✅   |   ❌    |     ✅      |   ❌   |     ❌     |
| LinkedIn   |   ❌   |   ❌   |   ✅    |     ✅      |   ❌   | Documento |
| Blog       |   ❌   |   ❌   |   ✅    |     ❌      |   ❌   |     ❌     |
| X          |   ❌   |   ✅   |   ❌    |     ✅      |   ❌   |     ❌     |

---


# Content Types

Todo tipo de conteúdo deverá seguir a estrutura abaixo.

```yaml
Tipo:

Formato:

Estrutura:
```

---

## Tipos de Conteúdo

---

### Vídeo

```yaml
Tipo:
  Vídeo

Formato:
  Horizontal

Estrutura:
  - Título
  - Introdução
  - Desenvolvimento
  - Conclusão
  - Hashtags
  - CTA
```

---

### Short

```yaml
Tipo:
  Short

Formato:
  Vertical

Estrutura:
  - Nome do arquivo
  - Gancho
  - Desenvolvimento
  - Hashtags
```

---

### Reel

```yaml
Tipo:
  Reel

Formato:
  Vertical

Estrutura:
  - Gancho
  - Conteúdo
  - Hashtags
```

---

### Story

```yaml
Tipo:
  Story

Formato:
  Vertical

Estrutura:
  - Conteúdo
  - Hashtags
```

---

### Artigo

```yaml
Tipo:
  Artigo

Formato:
  Texto

Estrutura:
  - Título
  - Introdução
  - Desenvolvimento
  - Conclusão
  - CTA
```

---

### Post

```yaml
Tipo:
  Post

Formato:
  Texto

Estrutura:
  - Conteúdo
  - Hashtags
```

---

### Carrossel

```yaml
Tipo:
  Carrossel

Formato:
  Sequência de Imagens

Estrutura:
  - Capa
  - Desenvolvimento
  - Encerramento
```

---

### Thumbnail

```yaml
Tipo:
  Thumbnail

Formato:
  Imagem

Estrutura:
  - Texto Principal
  - Elementos Visuais
```

---

### Banner

```yaml
Tipo:
  Banner

Formato:
  Imagem

Estrutura:
  - Elementos Visuais
```

---

### Logo

```yaml
Tipo:
  Logo

Formato:
  Imagem

Estrutura:
  - Elemento Principal
```

---

### Avatar

```yaml
Tipo:
  Avatar

Formato:
  Imagem

Estrutura:
  - Elemento Principal
```

---

### Imagem

```yaml
Tipo:
  Imagem

Formato:
  Imagem

Estrutura:
  - Descrição
```

---

## Regras

Os tipos de conteúdo nunca deverão definir:

- Projeto;
- Plataforma;
- SEO;
- Copywriting;
- Workflow.

Essas responsabilidades pertencem aos respectivos módulos.

---
