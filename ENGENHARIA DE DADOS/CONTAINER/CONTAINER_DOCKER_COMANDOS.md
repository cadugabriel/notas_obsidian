# 1. Referência de Comandos Essenciais

## Diagnóstico, Listagem e Inspeção

| **Escopo da Operação**      | **Comando Executável**                 | **Descrição**                                                  |
| --------------------------- | -------------------------------------- | -------------------------------------------------------------- |
| **Versão Global**           | `docker --version` ou `docker version` | Exibe a versão instalada do Docker Client e Server.            |
| **Ajuda Integrada**         | `docker <subcomando> --help`           | Mostra os parâmetros e flags aceitos por qualquer comando.     |
| **Listar Imagens**          | `docker images`                        | Lista todas as imagens baixadas localmente na máquina.         |
| **Listar Redes**            | `docker network ls`                    | Lista todas as redes criadas e disponíveis no Docker.          |
| **Listar Volumes**          | `docker volume ls`                     | Lista todos os volumes locais configurados para persistência.  |
| **Listar Rodando**          | `docker ps` ou `docker container ls`   | Lista apenas os containers ativos em execução neste momento.   |
| **Listar Todos**            | `docker ps -a`                         | Exibe todos os containers criados (em execução ou parados).    |
| **Apenas IDs**              | `docker ps -aq`                        | Retorna exclusivamente os IDs de todos os containers criados.  |
| **Logs do Sistema**         | `docker logs <container_name_or_id>`   | Imprime os registros de saída/erros gerados pelo container.    |
| **Inspeção de Baixo Nível** | `docker inspect <container_or_image>`  | Traz um payload JSON detalhado com as configurações do objeto. |

## Operações e Construção de Ambientes
  
| **Objetivo da Ação**    | **Comando Executável**                 | **Uso Prático**                                                          |
| ----------------------- | -------------------------------------- | ------------------------------------------------------------------------ |
| **Pesquisar Imagem**    | `docker search [valor]`                | Busca imagens públicas compatíveis disponíveis no Docker Hub.            |
| **Baixar Imagem**       | `docker pull [image_name]`             | Faz o download da imagem para a máquina local sem executá-la.            |
| **Compilar Dockerfile** | `docker build -t <nome_imagem> .`      | Constrói uma nova imagem baseada nas regras de um Dockerfile local.      |
| **Anexar Streams**      | `docker attach <container_id>`         | Acopla o terminal atual ao fluxo de entrada/saída de um container ativo. |
| **Parar Execução**      | `docker stop <id_ou_nome>`             | Envia um sinal SIGTERM para parar graciosamente o container.             |
| **Executar Compose**    | `docker-compose --env-file .env up -d` | Lê o `.env`, cria/atualiza os endpoints e roda em background (`-d`).     |

## Exclusão e Manutenção Geral (Limpeza)

| **O que deletar**     | **Comando Executável**             | **Impacto do Comando**                                                             |
| --------------------- | ---------------------------------- | ---------------------------------------------------------------------------------- |
| **Excluir Container** | `docker rm <container_id_ou_nome>` | Remove um container permanentemente (o container deve estar parado).               |
| **Excluir Imagem**    | `docker rmi <image_id_ou_nome>`    | Apaga a imagem do disco local (desde que nenhum container a utilize).              |
| **Excluir Rede**      | `docker network rm <network_id>`   | Remove uma rede customizada criada anteriormente.                                  |
| **Limpeza Geral**     | `docker system prune`              | Remove todos os containers parados, redes não usadas e caches pendentes.           |
| **Limpeza Total**     | `docker system prune -a`           | Remove **tudo** o que não estiver associado a um container ativo (inclui imagens). |

---

# 2. Dicionário de Subcomandos do Docker Engine

Estrutura completa de gerenciamento modular do ecossistema CLI:

| **Subcomando**      | **Função Principal**                                                                      |
| ------------------- | ----------------------------------------------------------------------------------------- |
| `builder`           | Gerencia os processos de compilação de imagens.                                           |
| `checkpoint`        | Cria imagens instantâneas do estado do container para restauração posterior.              |
| `commit`            | Salva o estado de alterações de um container em uma nova imagem estática.                 |
| `config`            | Administra os arquivos e contextos de configurações do Docker de forma nativa.            |
| `container`         | Agrupa todas as rotinas para gerenciar o ciclo de vida dos containers.                    |
| `context`           | Alterna e gerencia os contextos/motores de execução locais ou remotos.                    |
| `cp`                | Copia de forma transparente arquivos/pastas entre o host local e o container.             |
| `create`            | Prepara e cria a estrutura de um container a partir de uma imagem, mantendo-o parado.     |
| `diff`              | Analisa e lista alterações de arquivos feitas no sistema de disco do container.           |
| `events`            | Captura e expõe em tempo real os logs de eventos disparados pelo servidor Docker.         |
| `exec`              | Inicializa e roda um comando temporário diretamente em um container já ativo.             |
| `export`            | Exporta o conteúdo do sistema de arquivos do container em formato de arquivo `.tar`.      |
| `history`           | Lista as camadas geradas na criação cronológica de uma imagem específica.                 |
| `image`             | Agrupa ferramentas exclusivas de controle e empacotamento de imagens.                     |
| `import`            | Importa os dados empacotados de um arquivo tarball para criar uma imagem de disco.        |
| `info`              | Exibe dados de estatísticas sistêmicas do hardware e do motor do Docker.                  |
| `kill`              | Envia um sinal SIGKILL imediato para derrubar containers instantaneamente.                |
| `load`              | Restaura imagens a partir de um arquivo de backup `.tar` ou STDIN.                        |
| `login` / `logout`  | Autentica ou desconecta as credenciais locais em registries remotos.                      |
| `manifest`          | Manipula manifestos de imagens e gerencia compatibilidades multiarquitetura.              |
| `network`           | Cria, conecta e configura as pontes de redes lógicas isoladas.                            |
| `node`              | Executa comandos de controle de nós em clusters configurados em Docker Swarm.             |
| `pause` / `unpause` | Pausa temporariamente ou retoma todos os processos ativos em um container.                |
| `plugin`            | Gerencia as extensões e plugins de terceiros acoplados ao Docker.                         |
| `port`              | Mapeia as portas públicas do host associadas às portas privadas expostas.                 |
| `push`              | Sobe a imagem gerada localmente para um repositório remoto ou Docker Hub.                 |
| `rename`            | Renomeia o rótulo de identificação textual atribuído a um container.                      |
| `restart`           | Reinicializa de forma direta containers parados ou ativos.                                |
| `run`               | Cria um container a partir de uma imagem e inicializa o processo principal imediatamente. |
| `save`              | Salva uma ou mais imagens locais em um arquivo empacotado `.tar`.                         |
| `secret`            | Gerencia chaves e strings secretas de forma segura dentro de ambientes orquestrados.      |
| `service`           | Gerencia serviços criados dentro de arquiteturas orquestradas.                            |
| `stack`             | Administra stacks completas de microsserviços em orquestrações complexas.                 |
| `start`             | Inicializa um ou mais containers que foram parados anteriormente.                         |
| `stats`             | Retorna o stream real de consumo de hardware (CPU, memória, rede) dos containers.         |
| `swarm`             | Configura e gerencia engines de clusterização nativa (Docker Swarm).                      |
| `system`            | Comando macro para gerenciamento geral do sistema, limpeza e estatísticas do disco.       |
| `tag`               | Atribui marcadores ou versões de destino vinculados a uma imagem específica.              |
| `top`               | Lista a tabela clássica de processos linux ativos em background dentro do container.      |
| `trust`             | Define e gerencia políticas de assinatura digital e confiabilidade de imagens.            |
| `update`            | Reescreve limites dinâmicos de hardware (como memória limite) de um container rodando.    |
| `volume`            | Cria e configura diretórios protegidos para persistência permanente de dados.             |
| `wait`              | Bloqueia a execução no terminal até o container alvo finalizar, retornando o exit code.   |
