# Comando sobre PostgreSQL
> Restaurar la base de datos
```sh
  $ pg_restore  -h localhost -p 5432 -U postgres -d sgu -v datos.backup 
```
##### Doonde 
* [sgu] es la base de datos en postgres
* [datos.backup] es el abackup que vamos a restaurar en postgres
