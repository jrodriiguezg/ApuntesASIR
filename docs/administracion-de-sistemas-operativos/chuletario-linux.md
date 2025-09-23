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
    