# Zellij

https://zellij.dev/

Un terminal multiplexer.

## Instalacion

Para instlar el programa, si ya se tiene rust y sus componentes instalados, la forma mas facil es con cargo.

```shell
cargo install --locked zellij
```

## Configuracion

Para tener acceso al archivo de configuracion ejecutar los siguientes comandos.

```shell
mkdir ~/.config/zellij
```

```shell
zellij setup --dump-config > ~/.config/zellij/config.kdl
```

### Clipboard

Descomentar las siguientes lineas (suponiendo que se utilize xclip como clipboard manager):

La segundo linea la comento por que no podia copiar texto, por alguna razon esa opcion hace que falle.

```text
copy_command "xclip -selection clipboard"
mouse_mode false
```
