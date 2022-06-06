# Instalando postgres en fedora
Postgres es un gestor de base de datos opensource 

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

### Configurando el listener

### Configurando el acceso remoto

### Comando para restaurar una base de datos
```sh
  $ pg_restore  -h localhost -p 5432 -U postgres -d base -v datos.backup 
```
##### Doonde 
* [base] es la base de datos en postgres
* [datos.backup] es el abackup que vamos a restaurar en postgres
