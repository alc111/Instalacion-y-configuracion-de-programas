# Instalación y configuración de OhMyBash
La instalación es sumamente sencilla:
```
bash -c "$(curl -fsSL https://raw.githubusercontent.com/ohmybash/oh-my-bash/master/tools/install.sh)"
```
Si deseamos ponerle temas o personalizar la terminal, nos dirigimos al archivo bashrc(en caso de usar bash) y modificamos la siguiente línea:
```
OSH_THEME="font"
```
Cabe señalar que para el correcto funcionamiento del tema podría ser necesario instalar fuentes adicionales. En mi caso voy a ponerme el tema powerline-multiline, para el que necesitaré las powerline-fonts, coya instalación se llevaría a cabo de la siguiente manera:
```
sudo dnf install powerline-fonts
```
