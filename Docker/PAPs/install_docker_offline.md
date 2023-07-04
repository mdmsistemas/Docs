# Instalação offline do docker

1 - Em um computador com acesso a internet, baixe os pacotes **docker-ce**, **docker-ce-cli** e **containerd.io** da página a seguir correspondente a sua versão do Linux:

#### [Ubuntu 18.04](https://download.docker.com/linux/ubuntu/dists/bionic/pool/stable/amd64/)
#### [Ubuntu 20.04](https://download.docker.com/linux/ubuntu/dists/focal/pool/stable/amd64/)
#### [Ubuntu 22.04](https://download.docker.com/linux/ubuntu/dists/jammy/pool/stable/amd64/)

2 - Copie os arquivos para a máquina offline.

3 - Na máquina offline, instale os pacotes.
```
sudo dpkg -i *.deb
```
O docker daemon irá iniciar automaticamente e estará pronto para uso.
