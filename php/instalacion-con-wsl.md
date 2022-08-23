# Instalación con wsl

```
sudo add-apt-repository ppa:ondrej/php
sudo apt update
sudo apt upgrade
sudo apt install php8.0 apache2
```

Puedo instalar todas las versiones que quiera de php, si quiero saber cuales tengo&#x20;

```
sudo dpkg --get-selections | grep php
```

habilitar o desabilitar versiones de php

```
sudo a2enmod php8.0
sudo a2dismod php8.0
// y reiniciar apache
```

Si no funciona el apache localhost

```
sudo service apache2 --full-restart
```
