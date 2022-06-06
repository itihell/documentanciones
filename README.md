# Entorno en Fedora 36
Pasos para instalar los driver de nvidia en fedora 36 y prepar el entorno de desarrollo para trabajar con laravel, node, postgres.

* [Instalando driver NVIDIA](https://github.com/itihell/documentanciones/blob/main/driver_nvidia.md)
    * [Instalando RPM Fusión](https://github.com/itihell/documentanciones/blob/main/driver_nvidia.md#instlando-los-rpm-fusion-para-obtener-los-driver-privativos-dentro-de-fedora)  
    * [Instalando driver nvidia](https://github.com/itihell/documentanciones/blob/main/driver_nvidia.md#instalando-los-driver-de-nvidia)
* [Instalando NODE](https://github.com/itihell/documentanciones/blob/main/node.md)  
    * [Instalando NVM](https://github.com/itihell/documentanciones/blob/main/node.md#instalando-nvm)
    * [Instalando Node](https://github.com/itihell/documentanciones/blob/main/node.md#intalando-la-versi%C3%B3n-16-de-node)
    * [Definiendo por defecto](https://github.com/itihell/documentanciones/blob/main/node.md#definiendo-la-versi%C3%B3n-16-node-por-defecto)
* [Instalación de PHP](https://github.com/itihell/documentanciones/blob/main/php.md)
    * [Agregando el repositorio](https://github.com/itihell/documentanciones/blob/main/php.md#agregando-el-repo-a-fedora-36)
    * [Instalando php 7.4](https://github.com/itihell/documentanciones/blob/main/php.md#instalando-php-74)
    * [Instalando extensiones](https://github.com/itihell/documentanciones/blob/main/php.md#instalacion-extensi%C3%B3n)
    * [Instalando COMPOSER](https://github.com/itihell/documentanciones/blob/main/php.md#instalaci%C3%B3n-de-composer)
* [Instalación de Valet]()
    * [Requerimientos]()
    * [Instalación]()
    * [Configuración de dominios]()
    * [Configurando carpeta Raíz]()
* [Instalando PostgreSQL]()
    * [Instalación]()
    * [Configurando el usuario postgres]()
    * [Configurando el listener]()
    * [Configurando el acceso remoto]()
* [Instalación de docker]()
* [Instalación ZSH]()

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

> Reiniciando postgres
```sh 
  $ sudo systemctl restart postgresql
```

### Restaurando la base de datos de postgres 

```sh
 $  pg_restore  -h localhost -p 5432 -U postgres -d sgu -v datos.backup 
```

