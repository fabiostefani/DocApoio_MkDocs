# LINUX

Exemplos de comandos IaC

## Criar diretórios, grupos de usuários, vincular usuários aos grupos e permissões.
```
!/bin/bash

echo "Criando diretórios..."

mkdir /publico
mkdir /adm
mkdir /ven
mkdir /sec

echo "Criando grupos de usuários..."

groupadd GRP_ADM
groupadd GRP_VEN
groupadd GRP_SEC

echo "Criando usuários e vinculando aos seus grupos..."

useradd carlos -m -s /bin/bash -p $(openssl passwd 1234) -G GRP_ADM
useradd maria -m -s /bin/bash -p $(openssl passwd 1234) -G GRP_ADM
useradd joao -m -s /bin/bash -p $(openssl passwd 1234) -G GRP_ADM

useradd debora -m -s /bin/bash -p $(openssl passwd 1234) -G GRP_VEN
useradd sebastiana -m -s /bin/bash -p $(openssl passwd 1234) -G GRP_VEN
useradd roberto -m -s /bin/bash -p $(openssl passwd 1234) -G GRP_VEN

useradd josefina -m -s /bin/bash -p $(openssl passwd 1234) -G GRP_SEC
useradd amanda -m -s /bin/bash -p $(openssl passwd 1234) -G GRP_SEC
useradd rogerio -m -s /bin/bash -p $(openssl passwd 1234) -G GRP_SEC

echo "Permissões dos diretórios."

chown root:GRP_ADM /adm
chown root:GRP_VEN /ven
chown root:GRP_SEC /sec

chmod 770 /adm
chmod 770 /ven
chmod 770 /sec
chmod 777 /publico

echo "Finalizado"`
```

## Publicar servidor web

```
#!/bin/bash

echo "atualização do server"
apt-get update -y && apt-get upgrade -y

apt-get install apache2 -y
apt-get install unzip -y

echo "baixando e copíando a aplicação"
cd /tmp
wget https://github.com/denilsonbonatti/linux-site-dio/archive/refs/heads/main.zip
unzip main.zip
cd linux-site-dio-main
cp -R * /var/www/html/
```