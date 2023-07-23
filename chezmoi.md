# Chezmoi

https://github.com/twpayne/chezmoi

Manejador de dotfiles

## Instalacion

Al descargar con el siguiente comando guarda el binario en al carpeta `~/.local/bin`, por lo cual es una buena idea incluir el directorio en la variable **$PATH**.

```shell
sh -c "$(curl -fsLS get.chezmoi.io/lb)"
```

## Comandos utiles

A continuacion una lista de comandos utiles para chezmoi.

### Inicializar y clonar el ropositorio de los dotsfiles al mismo tiempo

``` shell
chezmoi init --apply git@github.com:$GITHUB_USERNAME/dotfiles.git
```

### Instalar, inicializar y clonar el repo al mismo tiempo

> **Nota**: Asegurarse de tener seteada la variable path.

```shell
sh -c "$(curl -fsLS get.chezmoi.io/lb)" -- init --apply $GITHUB_USERNAME
```

### Ir a la carpeta de chezmoi

```shell
chezmoi cd
```
