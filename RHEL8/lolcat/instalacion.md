# Instalación de lolcat
En primer lugar instalamos Ruby y comprobamos que lo hemos instalado:
```
sudo apt-get install ruby
ruby --version
```
Tras esto, descargamos el repositorio oficial de lolcat y descomprimimos el zip:
```
wget https://github.com/busyloop/lolcat/archive/master.zip
unzip master.zip
```
Por último, nos metemos en la carpeta recién obtenida tras decomprimir , nos dirigimos a la carpeta bin e instalamos:
```
cd lolcat-master/bin
sudo gem install lolcat
```
Para utilizarlo, ponemos un comando que imprima por terminal y le añadimos '| lolcat':
```
comando | lolcat
```
En mi caso, añadiré un neofetch con lolcat a mi archivo de bashrc para que salga cada vez que abra la terminal:
```
sudo micro .bashrc
#añadimos la siguiente línea al archivo
neofetch | lolcat
```
