# Recuperação offline de um container

1 - Em uma máquina com internet e com o docker instalado, baixe o container desejado no docker hub com o comando:
```
docker pull <nome_container>
```
Exemplo:
```
docker pull redis:alpine
```

2 - Salvar o container baixado do docker para um arquivo:
```
docker save -o redis-alpine.docker redis:alpine
```
Onde:\
**-o redis-alpine.docker:** Define o nome do arquivo.\
**redis:alpine:** O nome do container de origem.

3 - Copie o arquivo para o computador offline e recupere-o dentro do docker com o comando: 
```
docker load -i redis-alpine.docker
```
4 - Execute o container com o comando docker run. Uma explicação mais detalhada do docker run pode ser vista em:
#### [Recuperação de um container](container_online.md)
