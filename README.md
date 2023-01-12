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
 
 
