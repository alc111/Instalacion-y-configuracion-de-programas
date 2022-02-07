# Configuración de Alacritty
Para cambiar el tema base de alacritty o modificar aspectos de la terminal, emplearemos una herramienta llamada "alacritty-themes", que podemos instalar con npm, por lo que necesitaremos instalar en primer lugar nodejs.
## Instalación de NodeJS
La instalación de node es sencilla, simplemente añadimos el repo oficial e instalamos:
```
curl -sL https://rpm.nodesource.com/setup_17.x | bash -
sudo dnf install -y nodejs
```
## Instalación de alacritty-themes
Una vez tenemos el gestor npm, podemos instalar alacritty-themes fácilmente:
```
npm i -g alacritty-themes
```
Cuando se complete esta tarea, y antes de modificar nada, debemos crear el archivo de configuración de alacritty:
```
alacritty-themes --create
```
## Configuración de Alacritty
Para cambiar de tema basta con ejecutar el siguiente comando:
```
alacritty-themes
```
Si deseamos cambiar atributos en específico de la terminal, deberemos modificar el archivo de configuración creado anteriormente:
```
sudo micro .config/alacritty/alacritty.yml
```
El archivo de configuración permite un gran nivel de configuración, y ofrece una personalización destacable, pudiendo modificar gran cantidad de atributos, pero en nuestro caso priorizaremos sólo la transparencia y la decoración de la ventana:
```
#Descomentamos la siguiente línea
window:
#Añadimos el atributo opacity dentro de window
  opacity: 0.8
#Añadimos el atributo decorations y le ponemos 'none' si no queremos barras en la ventana o 'full' si sí queremos. En mi caso pondré 'none'
  decorations: none 
#Añadimos el atributo startup_mode(si alacritty se abre minimizado o no)
  startup_mode: Windowed
```
