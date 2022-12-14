# Instalação do Redis no Docker WSL

### 1 - Baixar a imagem 
No terminal Linux WSL, executar o comando:
```
sudo docker run -d --name redis -p 6379:6379 redis:alpine
```
**Atenção:** O comando -p 6379:6379 mapeia a porta 6379 do host para a porta 6379 do container. Cerifique-se de habilitar a porta 6379 em firewalls e afins.

### 2 - Confirmando a instalação
No terminal, executar o comando:

```
sudo docker ps -a
```

Se a instalação deu certo, uma saída similar ao seguinte conteúdo deverá ser exibida:

```
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                                       NAMES
c2eb96ad17bb   redis:alpine   "docker-entrypoint.s…"   10 minutes ago   Up 10 minutes   0.0.0.0:6379->6379/tcp, :::6379->6379/tcp   redis
```

### 3 - Iniciando o container junto com o boot do Windows

#### 3.1 - No terminal, navegar para a pasta /etc

#### 3.2 - Executar o seguinte comando:
```
sudo nano init-wsl
```

#### 3.3 - Criar o seguinte conteúdo no arquivo:
```
#!/bin/sh
service docker start
docker start redis
```

Salvar o arquivo com Ctrl + O, Sair do editor com Ctrl + X

#### 3.4 - Tornar o script executável com o seguinte comando:
```
sudo chmod +x /etc/init-wsl
```

#### 3.5 - De volta ao Windows, iniciar o agendador de tarefas (Task Scheduler).

#### 3.6 - Na árvore à esquerda, selecionar "Bibilioteca do agendador de tarefas" e, nas tarefas que carregarem à direita, dar botão direito -> Nova tarefa

![](./images/docker-run-boot-01.jpg)

#### 3.7 - Criar a tarefa com as seguintes configurações:

##### 3.7.1 - Aba Geral (General):
![](./images/docker-run-boot-02.jpg)

##### 3.7.3 - Aba Disparadores (Triggers):
![](./images/docker-run-boot-03.jpg)

##### 3.7.4 - Aba Ações (Actions):
![](./images/docker-run-boot-04.jpg)

Clicar em OK e salvar a nova tarefa.

