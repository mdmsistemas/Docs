# Recuperando um container Docker online

Para recuperar um container do docker de forma online, utilizamos o comando docker run. A imagem será baixada do repositório correspondente, e o container será criado.

Exemplo de recuperação do container redis:

```
docker run --name redis --restart always -p 6379:6379 redis:alpine
```

Onde:

**--name redis:** Define o nome do container para redis. Caso o nome não seja definido, o docker definirá um nome aleatório para o container (não recomendável).<br/><br/>
**--restart always:** O container sempre será iniciado automaticamente quando o docker foi iniciado com o Sistema Operacional.
**-p 6379:6379:** Mapeia a porta 6379 do interior do container para a porta 6379 exterior ao container.<br/><br/>
**redis:alpine:** O nome da imagem no repositório docker hub.

Resumidamente, estamos baixando a imagem redis:alpine do repositório do docker, criando um container com o nome redis a partir dela, e expondo a porta 6379 (porta default do Redis).

## Atenção
O comando docker run é utilizado apenas para criação do container pela primeira vez.<br/>
Caso um container já esteja criado e queiramos iniciar um container já criado, devemos utilizar o comando docker start. <br/>

Exemplo:<br/>
```docker start redis```

