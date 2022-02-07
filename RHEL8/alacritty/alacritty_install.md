# INSTALACION DE ALACRITTY
## Clonar el repositorio de Alacritty
En primer lugar clonamos el repositorio de alacritty y nos metemos en el:
```
git clone https://github.com/alacritty/alacritty.git
cd alacritty
```
## Instalar compilador de Rust
En segundo lugar hemos de instalar el compilador de Rust y comprobar su correcto funcionamiento. Al instalar el compilador cuando se nos pregunte qué tipo de instalación deseamos damos intro(default) y al terminar el proceso reiniciamos la terminal para que se guarden los cambios:
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
rustup override set stable
rustup update stable
```
## Dependencias de Alacritty
Antes de proceder con la compilación, instalamos una serie de dependencias:
```
sudo dnf install cmake freetype-devel fontconfig-devel libxcb-devel libxkbcommon-devel
sudo dnf group install "Development Tools"
```
## Compilación de Alacritty
Ahora ya podemos compilar correctamente su código fuente:
```
cargo build --release
```
## Terminfo
Ya hemos obtenido el binario deseado, y podemos probar su correcto funcionamiento con:
```
infocmp alacritty
```
Si no funciona correctamente el comando, ejecutamos el siguiente comando:
```
sudo tic -xe alacritty,alacritty-direct extra/alacritty.info
```
## Acceso directo
Si deseamos que alacritty sea visible desde el escritorio para ejecutarlo de manera gráfica debemos hacer lo siguiente:
```
sudo cp target/release/alacritty /usr/local/bin # or anywhere else in $PATH
sudo cp extra/logo/alacritty-term.svg /usr/share/pixmaps/Alacritty.svg
sudo desktop-file-install extra/linux/Alacritty.desktop
sudo update-desktop-database
```
## Manual Alacritty
Para instalar el manual de la terminal, también se ha de hacer manualmente:
```
sudo mkdir -p /usr/local/share/man/man1
gzip -c extra/alacritty.man | sudo tee /usr/local/share/man/man1/alacritty.1.gz > /dev/null
gzip -c extra/alacritty-msg.man | sudo tee /usr/local/share/man/man1/alacritty-msg.1.gz > /dev/null
```
## Autocompletar en Alacritty
Por último, para habilitar la función de autocompletar en alacritty para nuestra shell ejecutamos lo siguiente(en mi caso es bash, si tenéis otra mirad lo comandos del repo oficial de alacritty en Github):
```
echo "source $(pwd)/extra/completions/alacritty.bash" >> ~/.bashrc
```

