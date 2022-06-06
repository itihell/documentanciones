# Fedora 36

__Despues de instalar fedora 36 lo primero que se debe hacer es actualizar el sistema operativo para obtener las actulizaciones de los paquetes instalados__
### Actualizando el sistema operativo
```sh
sudo dnf -y update
```
### Instlando los RPM Fusion para obtener los driver privativos dentro de fedora  
Puedes acceder desde el sitio oficial de [RPM Fusion](https://rpmfusion.org/Configuration)  

```sh
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```  
- Agregadndo los media core
```sh 
sudo dnf groupupdate core
```
- Driver Multimedia  
```sh 
sudo dnf groupupdate multimedia --setop="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin 
```  
- Agregando al grupo de audio y video  
```sh
sudo dnf groupupdate sound-and-video  
```  
- Librerias 
```sh 
sudo dnf install rpmfusion-free-release-tainted
``` 
```sh 
sudo dnf install libdvdcss  
``` 
```sh 
sudo dnf install rpmfusion-nonfree-release-tainted
``` 
```sh
sudo dnf install \*-firmware
```  
#### **Nota** _Despues de instalar los RPM Fusión se recomiendo un reinicio del sistema_ 
### Instalando los driver de NVIDIA

Instalacion de driver para tarjetas NVIDIA modelos superiores a 2014 para mas información puede visitar la pagina oficial de RPM Fusion [driver nvidia](https://rpmfusion.org/Howto/NVIDIA#Installing_the_drivers)

```sh 
sudo dnf update -y # Actualizando el sistema
sudo dnf install akmod-nvidia # Driver privativo de nvidia
es opcional
``` 
* Librerias opcionales para el soporte de cuda
```sh 
sudo dnf install xorg-x11-drv-nvidia-cuda # Soporte de graficas con cuda esta opción 
sudo dnf install xorg-x11-drv-nvidia-cuda-libs
```
* Agregando caracteristicas de fedora workstation 
```sh 
sudo dnf groupupdate core
sudo dnf install fedora-workstation-repositories
``` 
