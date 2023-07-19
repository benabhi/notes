# Moodle V2

#educacion #proyecto


Para la version 2 de las plataformas de moodle vamos a crear un role de ansible que automatice el proceso de instalacion de Moodle, Base de datos, configuraciones de usuarios y demas con Ans
ible. Esto nos va a permitir avanzar mas rapido cuando se levanten otras plataformas.                                                                                                         
                                                                                                                                                                                              
El proyecto esta en `/home/benabhi/Documentos/Ansible/Estandar`.                                                                                                                              
La carpeta del role esta en `/home/benabhi/Documentos/Ansible/Estandar/role/moodle`                                                                                                           
El virtual environment de python `/home/benabhi/Documentos/Code/Ansible/venv`                                                                                                                 
                                                                                                                                                                                              
Antes de arrancar a hacer alguna cosa recordar siempre activar el **virtual_env**.                                                                                                            
                                                                                                                                                                                              
```shell                                                                                                                                                                                      
source /home/benabhi/Documentos/Code/Ansible/venv                                                                                                                                             
```                                                                                                                                                                                           
                                                                                                                                                                                              
Descargar moodle con git                                                                                                                                                                      
                                                                                                                                                                                              
Segun la [Documentacion Oficial](https://docs.moodle.org/402/en/Git_for_Administrators) hay que seguir estos pasos para descargar moodle con git.

```shell                                                                                                                                                                                      
cd /tmp                                                                                                                                                                                       
```                                                                                                                                                                                           
                                                                                                                                                                                              
Los comnandos de aqui en adelante hacen lo siguiente:                                                                                                                                         
                                                                                                                                                                                              
* El comando (1) inicializa el nuevo repositorio local como un clon del repositorio moodle.git 'upstream' (es decir, el basado en el servidor remoto). El repositorio upstream se llama 'origi
n' por defecto. Crea un nuevo directorio llamado moodle, donde descarga todos los archivos. Esta operación puede tardar un poco, ya que en realidad está obteniendo la historia completa de to
das las versiones de Moodle.                                                                                                                                                                  
* El comando (2) enumera todas las ramas disponibles.                                                                                                                                         
* Use el comando (3) para crear una nueva rama local llamada MOODLE_402_STABLE y configurarla para que rastree la rama remota MOODLE_402_STABLE del repositorio upstream.                     
* El comando (4) cambia a la rama local recién creada.                                                                                                                                        
                                                                                                                                                                                              
```shell                                                                                                                                                                                      
git clone git://git.moodle.org/moodle.git                                                                                                                                                     
```              

```shell                                                                                                                                                                                      
cd moodle                                                                                                                                                                                     
```                                                                                                                                                                                           
                                                                                                                                                                                              
```shell                                                                                                                                                                                      
git branch -a                                                                                                                                                                                 
```                                                                                                                                                                                           
                                                                                                                                                                                              
```shell                                                                                                                                                                                      
git branch --track MOODLE_402_STABLE origin/MOODLE_402_STABLE                                                                                                                                 
```                                                                                                                                                                                           
                                                                                                                                                                                              
```shell                                                                                                                                                                                      
git checkout MOODLE_402_STABLE                                                                                                                                                                
```                                                                                                                                                                                           
                                                                                                                                                                                              
## Cosas que hay que instalar en el servidor

* git                                                                                                                                                                                         
* php                                                                                                                                                                                         
* ...                                                                                                                                                                                         
                                                                                                                                                                                              
                                                                                                                                                                                              
## Requerimientos de Moodle 

NO CREAR EL CONFIG.PHP lo hace solo moodle!

instalar apache y php8.2

sudo apt install -y lsb-release gnupg2 ca-certificates apt-transport-https software-properties-common php8.2 php8.2-curl php8.2-zip php8.2-xml php8.2-mbstring php8.2-gd php8.2-intl php8.2-soap
sudo apt install php8.2-mysql

sudo add-apt-repository ppa:ondrej/php

max_input_vars = 5000

## Notas                                                                                                                                                                                      
                                                                                                                                                                                              
No olvidar que el git clone podria ser directamente en el root d ela aplicacion, asi luego para cuando haya que upgradear moodle podemos hacer un git pull.                                   
Seria una buena idea clonarlo en /srv/moodle y apuntar el root de apache a esa carpeta, que quede como algo generico para las posteriores plataformas.