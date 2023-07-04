# Executar o docker sem sudo

Por padrão, o Docker só pode ser executado pelo usuário **root**, logo devemos utilizar o comando sudo.\
Para evitar isso, devemos adicionar o usuário atual do Linux no grupo **docker**, que é criado na instalação do mesmo.

Execute os comandos abaixo na ordem descrita:
```
sudo usermod -aG docker ${USER}
```
```
su - ${USER}
```
Confime que o usuário atual está no grupo **docker** com o comando:
```
groups
```
Deverá exibir uma saída similar a:

sammy sudo **docker**
