# VM Setup

#util

Configuracion de mi hambiente de trabajo para desarrollo y sysadmin.

## Sistema Operativo

Como sistema operativo base elijo [Linux Mint](https://www.linuxmint.com/download.php) XFCE, probe un monton pero por lejos la mas estable y rapida es esta distro, por otro lado se ha mantenido a lo largo del tiempo sin tratar de inventar la rueda cuadrada.

### Packages

Dejo a continuacion la lista de paquetes y utilizades que se encuentran en los repositorios de mint. Mas adelante en el documento dejo los programas que requieren otros metodos de instalacion.

Paquetes importantes:

* git
* htop
* bat
* xclip
* ncdu
* duf
* ripgrep
* fd-find
* ncat
* w3m

```shell
sudo apt install git htop bat xclip ncdu duf ripgrep fd-find
```

## Fuentes

Cualquier fuente obtenida de [https://www.nerdfonts.com/](https://www.nerdfonts.com/) es viable, son modernas y vienen con iconos que estan utilizando las ultimas aplicaciones de terminal como `exa` por dar un ejemplo.

En este caso instalamos `JetBrainsMono Nerd Font` que es una de mis preferidas.

A continuacion dejo una serie de comandos para instalar la fuenta, la tengo gurdada en mi gdrive.

```shell
cd /tmp
```

```shell
mkdir -p ~/.local/share/fonts/
```

```shell
wget -O f.zip "https://drive.google.com/uc?export=download&id=1KmiObi1G1-xM-v7vnM__GxuLAZlMiZxn"
```

```shell
unzip f.zip -d ./f
```

```shell
mv ./f/*  ~/.local/share/fonts/
```

```shell
fc-cache -fv ~/.local/share/fonts/
```

## Programas

Otros programas que utilizo que no se pueden instalar directamente con apt o que requieren configuraciones especiales.

* [Glow](/home/benabhi/Documentos/Notes/Glow.md)
* [Broot](/home/benabhi/Documentos/Notes/Broot.md)
* [[Zellij]]

