## INSTALAR WSL2

- Abra o PowerShell como administrador e execute um por vez os dois comandos abaixo:
```console
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

- Reinicie sua máquina para concluir a instalação do WSL e atualizar para o WSL 2.

- Baixe o pacote mais recente:
[Clique aqui para baixar](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

- Execute o pacote de atualização baixado na etapa anterior. (Clique duas vezes para executar - serão solicitadas permissões elevadas, selecione 'sim' para aprovar esta instalação.)

- Abra o PowerShell e execute este comando para definir WSL 2 como a versão padrão ao instalar uma nova distribuição Linux:
```console
wsl --set-default-version 2
```

- Abra a Microsoft Store e selecione sua distribuição Linux favorita. (indicado instalar o ubuntu 20.04)
[https://aka.ms/wslstore](https://aka.ms/wslstore)

- Na página de distribuição, selecione "Obter".
Na primeira vez que vocÃª iniciar uma distribuição Linux recém-instalada, uma janela de console será aberta e vocÃª será solicitado a aguardar um ou dois minutos para que os arquivos sejam descompactados e armazenados em seu PC. Todos os lanÃ§amentos futuros devem levar menos de um segundo.

- Com o processo de instalação da distribuição Linux concluída, abra a distribuição escolhida (Ubuntu por default). Será solicitado a você a crição de um usuário e senha, crie esse acesso.

## CONFIGURAR DATA NO LINUX (UBUNTU)

- Com o ubuntu aberto verifique a data e hora digitando o comando abaixo
```console
date
```

- Verifique se a data e hora estão iguais ao do windows. Caso não esteja altere a data utilizando conforme indicado abaixo.
	- Exemplo: caso o windows esteja com a seguinte data/hora 23/07/2021 13:29:00 execute o comando:
```console
sudo date --set="2021-07-23 13:29:00.000"
```

## Download Docker

- Baixe e instale o docker no link abaixo ou no link mais atual no próprio site do docker
[https://desktop.docker.com/win/stable/amd64/Docker%20Desktop%20Installer.exe](https://desktop.docker.com/win/stable/amd64/Docker%20Desktop%20Installer.exe)

## RODAR O PROJETO

- Estando na pasta do projeto rode o docker composer para verificar se está tudo funcionando com o comando abaixo.
```console
docker-compose up -d
```

- Importe o banco para não ter erro ao abrir o projeto no navegador

## RODAR COMPOSER NO PROJETO

- Execute o comando abaixo para saber o nome do projeto. Obs: o nome do projeto fica na coluna NAME e não contém "mysql" fazendo parte do seu nome
```console
docker-compose ps
```

- Execute o comando abaixo substituindo NAME pelo nome do projeto descoberto anteriormente
```console
docker exec -it NAME bash
```

- Execute o comando abaixo para instalar o composer
```console
composer install && composer update
```

- Para sair do container execute o comando abaixo
```console
exit
```
