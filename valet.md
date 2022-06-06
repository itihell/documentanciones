# Instalación y configuración de valet
Valet Linux es un entorno de desarrollo de Laravel minimalistas para linux puedes visitar su sitio oficial en el siguiente [enlace](https://cpriego.github.io/valet-linux/index#introduction)  

### Requerimientos
Instalando los requisitos para fedora 36
```sh
sudo dnf install nss-tools jq xsel
```

### Configurando SELinux
* Abrir el archivo /etc/selinux/config
```sh 
sudo nano /etc/selinux/config
```
* Cambiar la linea SELINUX=enforcing por 
```sh 
SELINUX=enforcing # Antes
SELINUX=permissive # Asi debe quedar
```
Guardar el archivo y listo ya podras instalar valet si no te funciona prueba reiniciar el sistema despues de esta configuración

### Instalación
Para la instalación es necesario tener instalado composer ya que lo instalaremos valet via composer.  
```sh
composer global require cpriego/valet-linux 
```
### Agregando la variable de entorno 
Abra el archivo .bashrc o zshrc y al final de este escriba lo siguiente
```sh
export PATH="$PATH:$HOME/.config/composer/vendor/bin"
```

### Recargando bashrc o zshrc
```sh 
  $ source .bashrc # Si usa bash
  $ source .zshhrc # Si usa zsh
```
### Instalando valet
```sh  
valet install
``` 

### Definiendo dominios  
Es probable que despues de instalar valet te quedes sin internet es por ello que te recomiendo que configures el dominio que usaras con valet por ejemplo el dominio _**.test**_ de la siguiente manera.  
```sh
valet domain test
```
Si el problema del internet persiste debes de reiniciar tu adaptador de red con los siguientes comandos
```sh
sudo systemctl start systemd-resolved
sudo systemctl enable systemd-resolved
sudo systemctl restart NetworkManager
```

### Estableciendo carpeta raíz
La carpeta raiz es el folder en el cual vamos a almacenar todos nuestros proyectos creados en php ya sea laravel, worpress o drupal.  
* Creando la carpeta 
```sh
mdkir ~/Sites
```  
* Estableciendo la carpeta
```sh 
cd ~/Sites # Entramos a la carpeta Sites
valet park # Definimos la carpeta Sites como raiz
```

### Reiniciando Valet
Para levantar valet ejecutamos el siguiente comando
```sh
valet start # Iniciar valet
valet restart # Reiniciar valet despues de alguna modificación
```