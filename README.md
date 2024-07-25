# Como Funciona Tecnicamento o Docker

Docker é uma plataforma que facilita a criação, o envio e a execução de aplicações em containers.
Conteiners permitem que os desenvolvedores empacotem uma aplicação com todas as partes de que ela precisa, como bibliotecas e outras dependencias, e a enviem como um único pacote.
Aqui está uma visão técnica de como o Docker Funciona:

### 1 - Containers e Imagens:

#### 1.1 Imagem: 
É um snapshot imutável de um container. É um conjunto de camadas de read-only (somente leitura) que contém o sistema de arquivos e a aplicação necessária para executar um container. As imagens são criadas a partir de um Dockerfile.

#### 1.2 Container: 
É uma instância executável de uma imagem. Ele adiciona uma camada de read-write (leitura e escrita) em cima das camadas read-only da imagem e pode ser executado, parado, movido e deletado.

### 2 - Dockerfile:

- É um script de configuração que define como construir uma imagem Docker. Ele contém uma série de instruções, como FROM (imagem base), RUN (comandos a serem executados), COPY (copiar arquivos para o container), entre outros.

### 3 - Registries:

- Docker Hub é um serviço de registro público onde as imagens podem ser armazenadas e compartilhadas. Empresas também podem configurar registries privados para armazenar suas próprias imagens Docker.

### 4 - Arquitetura do Docker:

- Docker Engine: É o componente principal que permite construir e rodar containers Docker. É composto por três partes principais:
- Docker Daemon (dockerd): É um processo que gerencia containers Docker. Ele escuta requisições da API Docker e gerencia objetos Docker (imagens, containers, redes, volumes).
- Docker CLI (cliente): É uma interface de linha de comando que permite aos usuários interagirem com o daemon Docker via comandos como docker run, docker build, docker pull, etc.
- API REST: Interface de programação de aplicações que o Docker Daemon expõe para permitir a interação programática com o Docker.


### 5 - Isolamento e Segurança:

- Docker usa características de isolamento de recursos do kernel do Linux, como namespaces (isolamento de processos) e cgroups (controle de recursos), para garantir que os containers sejam executados de forma isolada uns dos outros.
- Namespaces: Provêm uma camada de isolamento, de modo que cada container tenha sua própria visão de recursos do sistema, como processos, rede, IDs de usuário e montagens de arquivos.
- Cgroups: Limitam a quantidade de recursos (CPU, memória, disco I/O, etc.) que um container pode usar.

### 6 - Volumes:

- Volumes são a forma preferida de persistir dados gerados e usados por containers Docker. Eles são gerenciados pelo Docker e são independentes do ciclo de vida de um container, garantindo que os dados persistam mesmo após a remoção do container.

### 7 - Networking:

- Docker permite criar redes isoladas para containers, permitindo que diferentes containers possam se comunicar entre si. O Docker fornece drivers de rede, como bridge (rede padrão), host, none, overlay e macvlan, para diferentes necessidades de rede.
  
Em resumo, o Docker simplifica a criação, o gerenciamento e a execução de aplicações em containers, proporcionando uma camada adicional de abstração e automação em torno de virtualização de nível de sistema operacional.
