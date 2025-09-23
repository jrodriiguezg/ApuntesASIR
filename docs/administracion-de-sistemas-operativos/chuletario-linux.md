# Comandos Linux 

## Comandos generales y de sistema 

- ```startx```:Inicia la ejecucion con pantalla grafica 
- ```halt```: Apaga el equipo
- ```reboot```: Reinicia la maquina 
- ```date```: Muestra la hora y fecha del sistema.
- ```clear```: Borra la pantalla de la terminal.
- ```man <comando>```: Muestra la ayuda o el manual de un comando.
- ```ps```: Muestra información sobre los procesos activos.
- ```echo [cadena]```: Repite una cadena. Con echo -e [cadena], habilita la interpretación de caracteres de escape.
- ```stat [fichero]```: Muestra el estado de un fichero. Con stat -f [fichero], muestra el estado del sistema de archivos.

## Sistema de ficheros y Directorios 

- ```cp```: Copia ficheros.
- ```rename```: Cambia el nombre de un fichero.
- ```rm```: Elimina un fichero o directorio.
- ```cd```: Cambia de directorio.
- ```mkdir```: Crea un directorio.
- ```pwd```: Muestra el directorio de trabajo actual.
- ```ls```: Lista el contenido de un directorio.
    - ```ls -la```: Muestra todos los ficheros, incluyendo los ocultos.
    - ```ls -a```: Lista todos los archivos, incluyendo los ocultos.
    -  ```ls -R```: Lista el contenido del directorio y todos sus subdirectorios de forma recursiva.
- ```cat [fichero]```:Muestra el contenido de un fichero.
    - ```cat -n [fichero]```: Muestra el contenido de un fichero numerando sus líneas.
- ```less [fichero]```: Muestra el contenido de un fichero, permitiendo avanzar y retroceder entre las páginas.
- ```more [fichero]```: Muestra un fichero de forma paginada.
- ```head [archivo]```: Muestra las primeras líneas de un archivo.
    - ```head -n [n] [archivo]```: Muestra las n primeras líneas de un archivo.
- ```tail [archivo]```: Muestra las últimas líneas de un archivo.
    - ```tail -n [n] [archivo]```: Muestra las n últimas líneas de un archivo.

- ```find [patron]```: Busca coincidencias con un patrón.
    - ```find [ruta] [patron]```: Busca coincidencias con el patrón dentro de una ruta.

## Gestión de Discos y Particiones

- ```fdisk```: Permite crear particiones.
- ```fsck```: Permite formatear una partición.
- ```df```: Indica el espacio libre del sistema de ficheros.
- ```du```: Indica el espacio utilizado.
- ```mount```: Monta un dispositivo (ej. mount /mnt/cdrom).
- ```Raidhotadd```: Añade discos en caliente a un RAID.
- ```Raidhotremove```: Elimina discos en caliente de un RAID.
- ```Raidreconf```: Copia datos de un disco duro a un RAID.
- ```Raidsetfaulty```: Marca un disco como defectuoso.
- ```Raidstart```: Inicia un sistema RAID.
- ```Raidstop```: Para un sistema RAID.

## Gestion de usuarios y contraseñas 

- ```pwconv```: Crea y actualiza el fichero  (/etc/shadow).
- ```pwuncov```: Desactiva las contraseñas de (/etc/shadow).
- ```adduser [usuario]```: Crea usuarios 
- ```useradd```: Crea usuarios pero preguntando por su informacion
- ```passwd [usuario]```: Establece la contraseña a un usuario 
- ```su [usuario]```: Cambia la sesion de la terminal a ese usuario 

## Cuota de disco 

- ```edquota usuario```: Asigna cuota a un usuario.
- ```edquota -g grupo```: Asigna cuota a un grupo.
- ```quota nomb_usuario```: Verifica la cuota de un usuario.
- ```quota -g nomb_grupo```: Verifica la cuota de un grupo.
- ```repquota```: Muestra un resumen de las cuotas.

## Instalación de Paquetes
**Familias debian**
- ```apt install```: Instala paquetes desde repositorios 
- ```dpkg -i [paquete]```: Instala paquetes 
**Familias RHEL**
- ```dnf install```: Instala paquetes desde repositorios
- ```rpm install -i [paquete]```: Instala paquetes 

## Comandos de red 

- ```ftp```: Cliente FTP.
```wget```: Gestor de descargas. ```wget -p -r -k URL``` descarga una web completa de forma recursiva.
- ```netstat -napt```: Muestra los puertos abiertos del sistema y los procesos asociados.
    - ```-n```: No resuelve nombres de dominio.
    - ```-a```: Muestra todas las conexiones.
    - ```-p```: Muestra el número y nombre del proceso.
    - ```-t```: Muestra solo conexiones TCP.

