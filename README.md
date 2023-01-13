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




# Conhecendo o Docker Hub

O Docker Hub é um grande repositório de imagens que podemos utilizar.

```bash
docker run ubuntu
```
Ao executar o comando acima, o docker realizar um fluxo de criação de containers:

Procura a imagem localmente -> Baixa a imagem caso não encontre localmente -> Valida o hash da imagem -> Executa o container.

Para que um container esteja em execução deve ter no mínimo um processo dentro dele para que o container fique vivo.




# Comandos necessários

Containers que estão em execução
```bash
docker ps
```
Maneira um pouco mais semântica 
```bash
docker container ls
```

Visualizar todos os containers, inclusive os que já não estão mais em execução
```bash
docker ps -a
docker container ls –a
```


Iniciar um container que esteja parado
```bash
docker start <container-id>
```

Parar um container que esteja rodando
```bash
docker stop <container-id>
```

Pausar um container
```bash
docker pause <container-id>
```

Iniciar um container pausado
```bash
docker unpause <container-id>
```

Remover um container específico:
 ```bash
docker container rm <container-id> --force
```


Interagir com um container de maneira interativa
```bash
docker run exec -it <container-id> bash
```

Executar o container e mantê-lo em execução sem precisar ficar dando sleep
```bash
docker run ubuntu bash
```

Indo mais além, podemos falar que queremos executá-lo em modo interativo, criando um container novo e já acessando diretamente o seu terminal
```bash
docker run -it ubuntu bash
```


FALTA FAZER
https://hub.docker.com/r/dockersamples/static-site

```bash
docker run -d dockersamples/static-site
```

Exibir o mapeamento de portas: 
```bash
docker port
```

Conseguimos mapear portas de um container com as flags -p e -P.

Informando que a porta 8080 de nosso host irá refletir na porta 80 do container:
```bash
docker run -d -p 8080:80 dockersamples/static-site
```
Acesse seu navegador localhost:8080 e veja a aplicação sendo carregada dentro de seu container.




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
 
Para encerrar as imagens que estão rodando:
 
```bash
docker-compose down
```
