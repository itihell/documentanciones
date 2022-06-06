# Requerimientos SGU
## Node
### Instalando nvm
NVM es un paquete que nos permite gestionar e instalar las versiones de node de manera dinamica puedes visitar el repoisitorio para linux en el siguiente [enlace](https://github.com/nvm-sh/nvm)
* Instlación
```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```
* Recargando los datos de origen de la consola 
 
Dependiendo de tu consola debes recargar los siguientes archivos (~/.bash_profile, ~/.zshrc, ~/.profile, or ~/.bashrc).

Posibles formas de hacerlo
```sh
source ~/.bashrc # Si usas Bash recuerda bash es la consola por defecto
source ~/.zshrc # Si usas zsh
```

> Instalando node
```sh
 $ nvm install v16.14.2 
```
> nvm alias default 6.11.5 
```sh
 $ nvm alias default v16.14.2 
```
##### NPM
> 8.5.0
