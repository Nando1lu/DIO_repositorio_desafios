### 							Criar e configurar GitHub 

1. ssh-keygen -t ed25519 -C email@email.com

2. *navegar ate a pasta que foi criada*

3. comando *'ls'* (lista os arquivos)

4. comando *'cat'*  (chave .pub)

5. copiar a chave e ir no github configurar (chave .ssh)

6. limpar terminal usar o *'ctrl + L'*

7. comando *'eval $(ssh-agent -s)'* 

8. *"ssh-add id_xxxxxxxxxxxx"* passa a chave que fui criada (privada)

   ----------------------------------------------------------------------------------------------------------------------

   Para clonar um repositorio basta ir no github ter o código ssh e utilizar no terminal bash o seguinte comando
   *'git clone + link ssh'*

​		token de acesso pessoal

​		ir no github e copiar o token de acesso pessoal, nesse caso pode se copiar o https do 				repositorio

​		ultilizar o comando *"git clone + https"*

____________________________________________________________________________
 *mkdir -> cria pasta*

comando "git-init" na pasta que queira iniciar
comando "ls -a" mostra arquivos ocultos

**COMANDOS PARA CONFIGURAR EMAIL E NICK_NAME** 

comando para configurar o git *"git config --global user.email 'email@email.com'"*
comando *"git config --global user.name Nando1lu"*

criar um arquivo *markdown ".md"*

**COMMIT**

comando *"git add  *"* pega tudo que esta no diretório de trabalho e adiciona pra *comitar*

comando *"git commit -m 'O comentário que quiser'"*

comando *"git status"*

Mover arquivos comando *"mv 'nome do arquivo' 'e a pasta de destino'"*

Criar index => *echo > README.md*

subir os arquivos

*git remote add origin https://github.com/.git*
		**(ORIGIN É UM APELIDO)**

*git remote  -v* ('mostra a conexão')

empurrar => *git push origin master*

**CONFLITOS**

comando *"git pull origin master"* puxa o repositório remoto

comando "rm -f .git/index.lock" exclui index.lock quando da erro
