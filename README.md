# learning-docker

# Entendendo o Docker 

## Porque os containers são mais leves?

Os container funcionam como um processo do nosso sistema operacional (host).

## Como garantem o isolamento?

Com os namespaces conseguimos garantir que cada container tenha a capacidade de se isolar em determinados camadas, como:

- PID - Provê isolamento dos processos rodando dentro do container
- NET - Provê isolamento das interfaces de rede
- IPC - Provê isolamento da comunicação entre processos e memória compartilhada
- MNT - Provê isolamento do sistema de arquivos/pontos de montagem
- UTS - Provê isolamento do kernel. Age como se o container fosse outro host

## Como o container funciona sem a necessidade de um sistema operacional?

Cada container possui um pedaço do kernel do linux, graças ao namespaces UTS.

## Como é a divisão de recursos do sistema?

Os recursos dos containers são gerenciados através de cgroups.

# Instalando o docker



# Conhecendo o Docker Hub

```bash
docker run ubuntu
```
Ao executar o comando acima, o docker realizar um fluxo de criação de containers:

  Procura a imagem localmente -> Baixa a imagem caso não encontre localmente -> Valida o hash da imagem -> Executa o container.

Para que um container esteja em execução deve ter no mínimo um processo dentro dele para que o container fique vivo.

# Comandos necesários

docker ps / docker container ls - quais container estão em execução
 
docker ps -a

# Docker Compose

https://docs.docker.com/compose/

Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration.

Install the docker: https://docs.docker.com/desktop/install/linux-install/
 
 # Subindo uma aplicação com YML
 
 Baixar o arquivo docker-compose.yml.
 
 Acesse pelo terminal do arquivo.
 
 Execute:
 
 ```bash
 docker-compose up -d
 ```
 
  No navegador, acesse a url localhost:3000/seed e em seguida localhost:3000 e veja que tudo continua funcionando como anteriormente.
 
 
