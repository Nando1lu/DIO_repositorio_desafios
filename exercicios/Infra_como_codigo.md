# **Infraestrutura como código** :page_with_curl:🖥️

### 	 Script de Criação de Estrutura de Usuários, Diretórios e Permissões

- ***IaC*** : é o gerenciamento e provisionamento da infraestrutura por meio de códigos, em vez de processos manuais.
- ***Controle de versão*** : via GitHub.
- ***Principais benefícios*** : Evitar o provisionamento manualmente e gerenciamento de servidores, sistemas operacionais, armazenamento e ect... Economizando tempo e padronizando as ações.

<img src=".\img\img_1.png" alt="" style="zoom: 200%;" />

###      Definições:

- Excluir diretórios, arquivos, grupos e usuários criados anteriormente;
- Todo provisionamento deve ser feito em um arquivo do tipo Bash
  Script;
- O dono de todos os diretórios criados será o usuário root;
- Todos os usuários terão permissão total dentro do diretório publico;
- Os usuários de cada grupo terão permissão total dentro de seu
  respectivo diretório:
- Os usuários não poderão ter permissão de leitura, escrita e execução
  em diretórios de departamentos que eles não pertencem;
- Subir arquivo de script criado para a sua conta no GitHub.

### 	Resolução:

1.Excluir usuários, quantas vezes for necessário;

```bash
root@servidor:/# userdel -r nome_usuario
```

2.Excluir  grupos, quantas vezes for necessário;

```bash
root@servidor:/# groupdel nome_grupo
```

3.Criar novo script:

- Criar diretório com o nome 'scripts' de preferencia na raiz, usando o ***nano*** criar um arquivo **'nome_arquivo.sh'**.

4.Dentro do arquivo criado:

```bash
#!/bin/bash

echo "Criando diretorios"
mkdir /publico
mkdir /adm
mkdir /ven
mkdir /sec
echo "Diretorios ok"

echo "criando os grupos"
groupadd GRP_ADM
groupadd GRP_VEN
groupadd GRP_SEC
echo "Grupos ok"

echo "Criando usuarios"
useradd carlos -c "Carlos" -s /bin/bash -m -p $(openssl passwd -crypt Senha123) -G GRP_ADM
useradd maria -c "Maria" -s /bin/bash -m -p $(openssl passwd -crypt Senha123) -G GRP_ADM
useradd joao -c "João" -s /bin/bash -m -p $(openssl passwd -crypt Senha123) -G GRP_ADM

useradd debora -c "Debora" -s /bin/bash -m -p $(openssl passwd -crypt Senha123) -G GRP_VEN
useradd sebastiana -c "Sebastina" -s /bin/bash -m -p $(openssl passwd -crypt Senha123) -G GRP_VEN
useradd roberto -c "Roberto" -s /bin/bash -m -p $(openssl passwd -crypt Senha123) -G GRP_VEN

useradd josefina -c "Josefina" -s /bin/bash -m -p $(openssl passwd -crypt Senha123) -G GRP_SEC
useradd amanda -c "Amanda" -s /bin/bash -m -p $(openssl passwd -crypt Senha123) -G GRP_SEC
useradd rogerio -c "Rogerio" -s /bin/bash -m -p $(openssl passwd -crypt Senha123) -G GRP_SEC
echo "Usuarios ok"

echo "Adicionando usuarios aos diretorios"
chown root:GRP_ADM /adm
chown root:GRP_VEN /ven
chown root:GRP_SEC /sec
echo "OK..."

echo "Dando permissão"
chmod 770 /adm
chmod 770 /ven
chmod 770 /sec
chmod 777 /publico
echo "permissao OK"

echo "Finalizado .............."
```

5.Apos salvar o arquivo, na mesma pasta, execute o seguinte comando para poder iniciar o script

```bash
root@servidor:/# chmod +x nome_arquivo.sh
```

6.É só executar 

```bash
root@servidor:/# ./nome_arquivo.sh
```

### **Resultado**

<img src=".\img\Captura de tela 2023-03-04 160839.png" alt="Captura de tela 2023-03-04 160839" style="zoom: 200%;" />