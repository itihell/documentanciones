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
