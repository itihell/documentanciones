# Instalando NVM en Fedora
## Node
### Instalando nvm
NVM es un paquete que nos permite gestionar e instalar las versiones de node de manera dinamica puedes visitar el repoisitorio para linux en el siguiente [enlace](https://github.com/nvm-sh/nvm)
* Instlación
```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```
* Verifica que al final de tu archivo bashrc o zshrc dependiendo el caso este la siguiente linea con tu editor de texto preferido  

__Abriendo el archivo__
```sh  
nano ~/.bashrc # Si usas nano recuerda si usas zsh es ~/.zshrc
vi ~/.bashrc # Si usas VI recuerda si usas zsh es ~/.zshrc
```
__Dato que debes verificar__
```sh  
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
``` 
Si no esta al final de tu archivo agregalo y guarda tu archivo.

### Recargando los datos de origen de la consola 

Dependiendo de tu consola debes recargar los siguientes archivos (~/.bash_profile, ~/.zshrc, ~/.profile, or ~/.bashrc).

Posibles formas de hacerlo
```sh
source ~/.bashrc # Si usas Bash recuerda bash es la consola por defecto
source ~/.zshrc # Si usas zsh
```

### Intalando la versión 16 de node
```sh
 $ nvm install v16.14.2 
```
### Definiendo la versión 16 node por defecto 
```sh
 $ nvm alias default v16.14.2 
```
Depues de desto ya podras ver las versiones de los paquetes instalados con los siguientes comandos.  
```sh
nvm -v # Para ver la versión de NVM
node -v # Para ver la versión de NODE 
npm -v # Para ver la versión de NPM
``` 
____
##### Paquetes instalados
- **Node**: 16.14.2  
- **NPM**: 8.5.0
