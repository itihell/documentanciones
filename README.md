# Entorno de desarrollo en linux

###  Instalando PHP
```sh
sudo apt install php-fpm
sudo apt install php-cli
sudo apt install php-curl
sudo apt install php-mbstring
sudo apt install php-mcryp
sudo apt install php-xml
sudo apt install php-zip
sudo apt install php-pgsql
```
* Ver la versión de php
```sh 
  $ php –version
```

* Actaulizando el sistema
```sh 
  $ sudo apt update
```
### Instalando composer!
> Antes de instalar composer debe estar instalado PHP
```sh
  $ sudo apt-get install curl
```
```sh
  $ curl -sS https://getcomposer.org/installer | php
```
```sh
  $ sudo mv ~/composer.phar /usr/local/bin/composer
```

### Instalando Valet Linux
> Anstes de instalar valet linux debe estar instalado composer
```sh
  $ composer global require cpriego/valet-linux
```
##### Agregando la variable de entorno 
Abra el archivo .bashrc y al final de este escriba lo siguiente
```sh
export PATH="$PATH:$HOME/.config/composer/vendor/bin"
```
Luego ejecute el comando 
```sh
  $ valet install
```
Sida error al momento de instalar ejecutar el comando siguiente para instalara dependencias
```sh
  $ sudo apt-get install network-manager libnss3-tools jq  xsel
```

Luego hacemos los siguiente para crear un carpeta en la cual estaran alojados nuestro proyectos de laravel
```sh
  $ cd 
  $ mkdir Site
  $ cd Site
  $ valet park
```

##### Levantando Valet
Para levantar valet ejecutamos el siguiente comando
```sh
  $ valet start
```
### Instalando PostgreSQL
Para gestionar las bases de datos usaremos postgres
> Instalación
```sh 
  $ sudo apt install postgresql postgresql-client
```
> Ver el estado 
```sh 
  $ systemctl status postgresql.service 
```
> Archivos a configurar dependiendo de la versión 
```sh
  $ sudo nano  /etc/postgresql/12/main/postgresql.conf
  $ sudo nano /etc/postgresql/12/main/pg_hba.conf
```
> Reiniciando postgres
```sh 
  $ sudo systemctl restart postgresql
```
> Cambiando la clave del usuario postgres
```sh
  $ sudo su - postgres
  $ psql -c "alter user postgres with password '12345678'"
```
> Agregando el driver de postgres a php 
```sh 
  $ sudo apt -y install php-pgsql
```
### Restaurando la base de datos de postgres 

```sh
 $  pg_restore  -h localhost -p 5432 -U postgres -d sgu -v datos.backup 
```

