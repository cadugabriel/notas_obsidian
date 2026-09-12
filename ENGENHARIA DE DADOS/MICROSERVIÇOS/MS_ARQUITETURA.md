# OBJETIVO

Notas relacionadas a arquitetura de microserviços.

---

# 🌐 Arquitetura de Microserviços: Comunicação, APIs RESTful e Padrões HTTP

## 1. Fundamentos e Paradigmas: REST vs SOAP

A escolha da tecnologia de comunicação impacta diretamente o acoplamento e a escalabilidade dos microserviços.

* **API (Application Programming Interface):** Conjunto de rotinas e padrões de programação para acesso a uma plataforma ou software web, servindo como back-end compartilhado entre aplicações Web e nativas.

* **Recurso (*Resource*):** Elemento de informação manipulado por um ID global. Sua nomeação deve ser obrigatoriamente estruturada com **substantivos**, nunca verbos (Ex: `/usuarios`).

### Tabela Comparativa: Modelos de Integração

| Característica          | REST (*Representational State Transfer*) | SOAP (*Simple Object Access Protocol*)     |
| :---------------------- | :--------------------------------------- | :----------------------------------------- |
| **Classificação**       | Modelo Arquitetural                      | Protocolo de Comunicação Oficial           |
| **Transporte**          | Requisições HTTP Simples                 | Chamadas RPC envelopadas em mensagens HTTP |
| **Formatos Suportados** | Múltiplos: JSON, XML, YAML, etc.         | Estritamente restrito a XML                |

---

## 2. As Restrições Criptográficas de Roy Fielding (*Constraints*)

Para que um sistema distribuído adote o modelo REST, ele precisa atender a um conjunto de regras de design (*constraints*) introduzidas por Roy Fielding em sua tese de Ph.D. no ano de 2000:

  1. **Cliente-Servidor:** Separação das responsabilidades de interface e back-end, garantindo evolução e escalabilidade independentes.

2. **Stateless (Sem Estado):** Cada requisição deve conter absolutamente todas as informações necessárias para seu processamento; o servidor não armazena contextos de requisições anteriores.

3. **Cache:** O sistema deve sinalizar quais respostas podem ser mantidas em cache para otimizar a performance da rede.

4. **Sistema em Camadas:** Capacidade de encadear elementos intermediários transparentes (como Balanceadores de Carga) para suportar grandes volumes distribuídos.

5. **Interface Uniforme:** Padronização centrada em recursos, mensagens autodescritivas e hipermídia.

6. **Código Sob Demanda (*Opcional*):** Envio de scripts executáveis (como JavaScript) para expandir a flexibilidade do cliente temporariamente.

---

## 3. Catálogo Semântico de Métodos HTTP

Os verbos HTTP definem a intenção técnica de cada chamada na malha de serviços.

### Métodos Avançados e Auxiliares

* **PATCH:** Executa modificações parciais (alteração de campos específicos de um recurso). Difere do **PUT**, que exige a substituição integral do recurso.

* **HEAD:** Idêntico ao GET, mas o servidor retorna apenas os cabeçalhos (*headers*), omitindo o corpo (*body*). Útil para checar conexões e existência de dados.

* **OPTIONS:** Permite que o cliente consulte os requisitos e métodos permitidos (como políticas de CORS) para um recurso.

* **TRACE:** Ecoa a requisição original de volta ao remetente, permitindo inspecionar alterações feitas por proxies ou intermediários.

* **CONNECT:** Cria um túnel TCP/IP transparente, comumente usado para habilitar conexões criptografadas com SSL/TLS (HTTPS) através de proxies.

### Propriedades de Segurança dos Métodos

| Propriedade                  | Definição                                                                                                                          | Métodos Correspondentes                                     |
| :--------------------------- | :--------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------- |
| **Métodos Seguros (*Safe*)** | Operações de leitura que não geram qualquer efeito colateral nos estados do cliente ou servidor[cite: 3].                          | `GET`, `HEAD`[cite: 3]                                      |
| **Idempotência**             | Operações matemáticas/computacionais que produzem o mesmo impacto final, quer sejam executadas uma ou dez vezes seguidas[cite: 3]. | `GET`, `HEAD`, `PUT`, `DELETE`, `OPTIONS`, `TRACE`[cite: 3] |

---

## 4. O Modelo de Maturidade de Richardson (RMM)

  Proposto por Leonard Richardson, este modelo divide a jornada de adoção do REST em 4 níveis progressivos.

```text
[ Glória do REST ] ─── Nível 3: HATEOAS (Controles de Hipermídia)
▲
├────────────── Nível 2: Verbos HTTP (Semântica correta e status)
├────────────── Nível 1: Recursos (Modelagem de URIs por substantivos)
└────────────── Nível 0: POX (Apenas transporte HTTP / RPC)
```

### Detalhamento dos Níveis

#### Nível 0: POX (Plain Old XML / RPC)

- O protocolo HTTP é subutilizado, agindo unicamente como transporte para chamadas de procedimentos remotos (RPC).

- Usa URIs com verbos e ações embutidas (Ex: `POST /salvarCliente` ou `GET /deletarCliente/1`).

- **Falha Semântica comum:** Retornar erros de negócio envelopados em respostas com status `200 OK` (Ex: retornar erro interno em um JSON/XML, confundindo elementos de gateway e proxies).


#### Nível 1: Recursos

- A API passa a ser modelada e organizada com foco em **recursos** únicos.

- O cliente interage com a URI correspondente à entidade e não com múltiplos endpoints de verbos (Ex: `/cliente/1` em vez de `/buscarCliente/1`).


#### Nível 2: Verbos HTTP

- O HTTP ganha papel semântico; usa os métodos (`GET`, `POST`, `PUT`, `DELETE`) de acordo com sua finalidade nativa.

- Garante o uso apropriado dos códigos de status HTTP (Ex: retornar `201 Created` acompanhado do cabeçalho `Location` contendo a URL de acesso ao novo recurso criado).

  
#### Nível 3: HATEOAS (_Hypermedia as the Engine of Application State_)

- O nível obrigatório para que uma API seja categorizada como puramente **RESTful** segundo Roy Fielding.

- A representação retornada pelo servidor descreve seu estado atual e fornece os links de relacionamentos dinâmicos (`<link rel="..." href="..." />`) para guiar as próximas interações possíveis do cliente.

## 5. Media Types e Negociação de Conteúdo

O formato do payload trocado entre microserviços é gerenciado dinamicamente via cabeçalhos HTTP.

- **Definição:** Uma string padronizada formada por `tipo/subtipo` (Ex: `application/json`, `application/xml`) acompanhada opcionalmente de parâmetros (Ex: `charset=UTF-8`).

- **Content-Type vs Accept:**

- `Content-Type`: Identifica o formato do dado enviado no corpo da requisição corrente (Ex: payload de um POST).

- `Accept`: Sinaliza ao servidor qual o formato de dado que o cliente deseja e espera receber como resposta.

### Fator de Qualidade (_Quality Factor_)

O cabeçalho `Accept` permite encadear múltiplos formatos de preferência usando o parâmetro `q` (de 0 a 1) para indicar prioridade:

```Bash
curl mockbin.org/request -H "Accept: application/json; q=0.5, application/yaml; q=0.1"
```
