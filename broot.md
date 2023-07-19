# Broot

https://github.com/Canop/broot

Fuzzy Finder con estilo "tree", muy bueno para encontrar archivos y directorios, tiene opciones avanzadas como preview de archivos y buscardo de patrones de texto en los mismos.

## Instlacion

```shell
cd /tmp
```

```shell
curl -o broot -L https://dystroy.org/broot/download/x86_64-linux/broot
```

```shell
sudo mv broot /usr/local/bin
```

```shell
sudo chmod +x /usr/local/bin/broot
```

```shell
broot
```

Al ejecutar el comando nos pregunta si queremos finalizar la isntalación y damos enter directamente, el comportamiento por derecto es "**Y**".

```shell
source ~/.bashrc
```

## Configuraciones

### Default Flags

Para hacer que el comando siempre ejecute los parametros `-pd` que es de permisos y fechas de archivos, editar el archivo de configuracion `~/.config/broot/conf.hjson`.

Descomentar la linea **defaukt_flags** y editarla para que quede asi.

```text
defaults_flags: pd
```

### Icon Theme

Para mostrar iconos de archivos hay que descomentar la linea **icon_theme** y configurar.

```text
icon_theme: vscode
```

Es necesario descargar la fuente del siguiente enlace [https://github.com/Canop/broot/blob/main/resources/icons/vscode/vscode.ttf](https://github.com/Canop/broot/blob/main/resources/icons/vscode/vscode.ttf) a instalarla. **Nota** con esto ultimo, tuve que descargarla por el navegador e instalarla con doble click en la GUI, no me dejo por consola. En el siguiente enlace hay mas info sobre los iconos [https://dystroy.org/broot/icons/](https://dystroy.org/broot/icons/).