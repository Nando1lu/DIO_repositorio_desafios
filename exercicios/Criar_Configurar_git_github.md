ssh-keygen -t ed25519 -C luizfog1@gmail.com
*navegar ate a pasta que foi criada*
comando 'ls'
comando 'cat'na chave .pub
copiar achave e ir no github configurar
limpar terminal usar o 'ctrl + L'
comando 'eval $(ssh-agent -s)'
passar a chave que acabamos de criar 
"ssh-add id_**********"

para clonar um repositorio basta ir no github ter o codigo ssh e ultilizar no terminal bash o seguinmte comando
'git clone + link ssh'

token de acesso pessoal

ir no github e copiar o token de acesso pessoal, nesse caso pode se copiar o hhtps do repositorio

ultilizar o comando "git clone + https"

____________________________________________________________________________
 mkdir -> cria pasta

comando "git-init" na pasta que queira iniciar
comando "ls -a" mostra arquivos ocultos

COMANDOS PARA CONFIGURAR EMAIL E NICK_NAME 

comando para configurar o git "git config --global user.email 'luizfog1@gmail.com'"
comando "git config --global user.name Nando1lu"

criar um aquivo markdown ".md"

COMMIT

comando "git add *" pega tudo que esta no diretorio de trabalho e adiciona pra comitar

comando "git commit -m 'commit inicial'"

comando "git status"

Mover arquivvos comando "mv 'arquivo' 'e a pasta de destino'"

Criar index => echo > README.md

subir os arquivos

git remote add origin https://github.com/Nando1lu/livto-receitas.git
		(ORINIG É UM APELIDO)

git remote  -v

empurrar => git push origin master

CONFLITOS

comando "git pull origin master"

TRACKED OU UNTRACKED
