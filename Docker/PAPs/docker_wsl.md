# Instalação do Docker no Windows

## 1 - Preparação: Instalação do Linux no Windows

### 1.1 - Acessar no Windows a opção "Ativar ou desativar recursos do Windows" ou, em inglês, "Turn Windows features on and off".
![](./images/install-01.jpg)

### 1.2 - Ativar as opções "Hyper-V" e "Subsistema do Windows para Linux"
![](./images/hyperv.jpg)\
![](./images/install-02.jpg)

### 1.3 - Após marcar esta opção, reinicie o computador.

### 1.4 - Habilitar recursos de Máquina Virtual

Inicie o Windows Powershell com direitos administrativos e rode o seguinte comando:
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

### 1.5 - Baixar e instalar a atualização de Kernel para Linux:

https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi

### 1.6 - Setar o WSL2 como versão padrão

Inicie o Windows Powershell com direitos administrativos e rode o seguinte comando:
```
wsl --set-default-version 2
```

### 1.7 - Instalar o Ubuntu for Windows
```
wsl --install -d Ubuntu
```

### 1.8 - Conferindo a instalação

Execute no powershell do windows o comando:
```
wsl -l -v
```

Deverá exibir uma mensagem similiar a:

```
  NAME      STATE           VERSION
* Ubuntu    Running         2
```

```
sudo update-alternatives --set iptables /usr/sbin/iptables-legacy
sudo update-alternatives --set ip6tables /usr/sbin/ip6tables-legacy
```
