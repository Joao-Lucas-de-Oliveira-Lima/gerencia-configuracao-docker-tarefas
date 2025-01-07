
# Gerenciamento de Configuração com Docker

## Índice

- [Sobre](#sobre)
- [Primeiros Passos](#primeiros-passos)
  - [Pré-requisitos](#pré-requisitos)
  - [Instalação](#instalação)
    - [Gerar Build da Imagem](#gerar-build-da-imagem)
    - [Build do Container](#build-do-container)
- [Uso](#uso)

## Sobre

Este projeto fornece uma solução de gerenciamento de configuração para conteneirizar uma aplicação com Docker. Ele utiliza Docker Compose e bind mounts para armazenar arquivos gerados pelo container no host. A aplicação realiza logs de nível TRACE, salvando-os no caminho `/logs/dockerVolumeTest.log` dentro do container, que é mapeado para `./logs` no host.

## Primeiros Passos

### Pré-requisitos

Antes de começar, certifique-se de ter instalado:

- [Java JDK 21](https://www.oracle.com/java/technologies/javase/jdk21-archive-downloads.html)
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)

### Instalação

#### Gerar Build da Imagem

Para compilar a aplicação e gerar o arquivo `.jar`, execute o comando abaixo usando o Maven Wrapper:

```bash
./mvnw clean package
```

Isso limpará a pasta `/target` (se existir) e gerará o `.jar` compilado da aplicação.

#### Build do Container

Crie e inicie o container Docker usando o seguinte comando:

```bash
docker compose up -d
```

Isso irá construir e executar a imagem Docker especificada no arquivo `Dockerfile`.

## Uso

Após executar o container, a aplicação estará disponível em:  

**[http://localhost:3003/api](http://localhost:3003/api)**


Os logs gerados podem ser encontrados em `./logs/dockerVolumeTest.log` no host.

---