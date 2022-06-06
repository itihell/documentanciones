# Fedora 36

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
