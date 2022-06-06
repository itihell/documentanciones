# Instalación de PHP 7.4 en fedora 36

### Agregando el repo a fedora 36
```sh  
sudo dnf -y update # Actualizando el sistema operativo  
sudo dnf -y install https://rpms.remirepo.net/fedora/remi-release-35.rpm
```

### Instalando PHP 7.4
```sh  
sudo dnf config-manager --set-enabled remi
sudo  dnf module reset php
sudo dnf module install php:remi-7.4
```
* Probando la versión de php
```sh
php -v
```
### Instalacion extensión
* Extesniones
```sh
sudo dnf install php  php-cli php-fpm php-pgsql php-zip php-devel php-gd php-mcrypt php-mbstring php-curl php-xml php-pear php-bcmath php-json php-soap
``` 
### Instalación de composer
* Instalación
```sh
  $ curl -sS https://getcomposer.org/installer | php
```
* Moviendo composer
```sh
  $ sudo mv ~/composer.phar /usr/local/bin/composer
```

> Para ver los modulos instalados en php podemos usar el comando 
```sh
php --modules 
```