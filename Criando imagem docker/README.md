# Imagem Docker

## Criando uma imagem Docker

Acesse o diretório que contém esse arquivo pelo terminal,
depois execute: 
```bash
docker build -t <seu-nome-de-usuario-do-docker-hub>/app-node:1.0 .
```

O arquivo Dockerfile possui as configurações para a geração de uma imagem docker.

Para saber mais sobre parametros possíveis para configurar: [Dockerfile reference](https://docs.docker.com/engine/reference/builder/)

Depois de criar a imagem, visualize as imagens existentes na máquina:
```bash
docker images
```

Agora suba a imagem:
```bash
docker run -d -p 8080:3000 <seu-nome-de-usuario-do-docker-hub>/app-node:1.0
```
