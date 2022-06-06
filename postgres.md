# Instalando postgres en fedora
Postgres es un gestor de base de datos opensource 
### Instalación
Puedes ir al siguiente [enlace](https://www.postgresql.org/download/linux/redhat/) para que puede especificar la versión que deseas en este caso instalaremos la versión 13 de postgreSQL.

```sh  
# Agregadndo el respositorio RPM Oficial de postgres:
sudo dnf install -y https://download.postgresql.org/pub/repos/yum/reporpms/F-36-x86_64/pgdg-fedora-repo-latest.noarch.rpm

# Instalando posgres:
sudo dnf install -y postgresql13-server

# Configuraciones de inicialización automatica de postgres:
sudo /usr/pgsql-13/bin/postgresql-13-setup initdb
sudo systemctl enable postgresql-13
sudo systemctl start postgresql-13
``` 
### Configurando el usuario postgres
Por defecto el usuario de postgres cuando se instala no se configura por ello es que debemos hacerlos postinstalación
```sh
sudo su - postgres
psql -c "alter user postgres with password '12345678'" 
```
### Copiando archivos para la configuración
```sh
# Archivo de configuración de postgres
sudo cp /usr/pgsql-13/share/postgresql.conf.sample /usr/pgsql-13/share/postgresql.conf
# Archivo de configuracion para replicación y acceso remoto
sudo cp /usr/pgsql-13/share/pg_hba.conf.sample /usr/pgsql-13/share/pg_hba.conf

```
### Configurando el listener
Para configurar el listener del servidor y permitir que este escuche las peticiones de cualquier origen debemos configurar el archivo postgresql.conf

Busquemos la linea listen_addresses = 'localhost'
```sh
# Comando para abrir el archivo
sudo nano /usr/pgsql-13/share/postgresql.conf

listen_addresses = 'localhost' # Linea original

listen_addresses = '*' # Dejarlo de esta manera para que escuche todas las peticiones
``` 
Guardamos el archivo postgresql.conf, y con estos pequeños cambios ya el servidor escuchara las peticiones de cualquier origen.
### Configurando el acceso remoto
```sh
# Comando para abrir el archivo
sudo nano /usr/pgsql-13/share/pg_hba.conf 

# Configuración original
# IPv4 local connections:
host    all             all             127.0.0.1/32            @authmethodhost@

# Configuración que debe quedar
# IPv4 local connections:
host    all             all             all                     @authmethodhost@

```

### Reiniciando postgreSQL
Despues de todos estos cambios debemos reiniciar el servicio de postgres para que estos cambios puedan surtir efecto

```sh
# Recargando configuración
sudo systemctl reload postgresql-13

# Reiniciando postgreSQL
sudo systemctl restart postgresql-13 

# Ver el estado de postgres 
sudo systemctl status postgresql-13
``` 
### Comando para restaurar una base de datos
```sh
  $ pg_restore  -h localhost -p 5432 -U postgres -d base -v datos.backup 
```
##### Doonde 
* [base] es la base de datos en postgres
* [datos.backup] es el abackup que vamos a restaurar en postgres
