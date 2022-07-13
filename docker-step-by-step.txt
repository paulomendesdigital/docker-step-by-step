## INSTALAR WSL2

- Abra o PowerShell como administrador e execute um por vez os dois comandos abaixo:
```console
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

- Reinicie sua mÃ¡quina para concluir a instalaÃ§Ã£o do WSL e atualizar para o WSL 2.

- Baixe o pacote mais recente:
[Clique aqui para baixar](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

- Execute o pacote de atualizaÃ§Ã£o baixado na etapa anterior. (Clique duas vezes para executar - serÃ£o solicitadas permissÃµes elevadas, selecione 'sim' para aprovar esta instalaÃ§Ã£o.)

- Abra o PowerShell e execute este comando para definir WSL 2 como a versÃ£o padrÃ£o ao instalar uma nova distribuiÃ§Ã£o Linux:
```console
wsl --set-default-version 2
```

- Abra a Microsoft Store e selecione sua distribuiÃ§Ã£o Linux favorita. (indicado instalar o ubuntu 20.04)
[https://aka.ms/wslstore](https://aka.ms/wslstore)

- Na pÃ¡gina de distribuiÃ§Ã£o, selecione "Obter".
Na primeira vez que vocÃª iniciar uma distribuiÃ§Ã£o Linux recÃ©m-instalada, uma janela de console serÃ¡ aberta e vocÃª serÃ¡ solicitado a aguardar um ou dois minutos para que os arquivos sejam descompactados e armazenados em seu PC. Todos os lanÃ§amentos futuros devem levar menos de um segundo.

- Em seguida, vocÃª precisarÃ¡ criar uma conta de usuÃ¡rio e senha para sua nova distribuiÃ§Ã£o Linux .
[https://docs.microsoft.com/en-us/windows/wsl/user-support](https://docs.microsoft.com/en-us/windows/wsl/user-support)

## CONFIGURAR DATA NO LINUX (UBUNTU)

- Com o ubuntu aberto verifique a data e hora digitando o comando abaixo
date

- Verifique se a data e hora estÃ£o iguais ao do windows. Caso nÃ£o esteja altere a data utilizando conforme indicado abaixo.
	- Exemplo: caso o windows esteja com a seguinte data/hora 23/07/2021 13:29:00 execute o comando:
```console
sudo date --set="2021-07-23 13:29:00.000"
```

## RODAR O PROJETO

- Baixe e instale o docker no link abaixo ou no link mais atual no prÃ³prio site do docker
[https://desktop.docker.com/win/stable/amd64/Docker%20Desktop%20Installer.exe](https://desktop.docker.com/win/stable/amd64/Docker%20Desktop%20Installer.exe)

- Estando na pasta do projeto rode o docker composer para verificar se estÃ¡ tudo funcionando com o comando abaixo.
```console
docker-compose up -d
```

- Importe o banco para nÃ£o ter erro ao abrir o projeto no navegador

## RODAR COMPOSER NO PROJETO

- Execute o comando abaixo para saber o nome do projeto. Obs: o nome do projeto fica na coluna NAME e nÃ£o contÃ©m "mysql" fazendo parte do seu nome
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