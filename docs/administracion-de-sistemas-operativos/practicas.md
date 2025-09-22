# Practica 1 - COMANDOS LINUX REPASO GENERAL

1. Crear los directorios dir1, dir2 y dir3 en un directorio PRUEBA. Dentro de dir1 crear el
directorio dir11. Dentro del directorio dir3 crear el directorio dir31. Dentro del directorio
dir31, crear los directorios dir311 y dir312.

```bash
mkdir prueba && mkdir prueba/dir1 prueba/dir2 prueba/dir3 prueba/dir1/dir11 prueba/dir3/dir31 prueba/dir3/dir31/dir311 prueba/dir3/dir31/dir312
```
**Explicacion:**
    - ```mkdir```: Crea directorios 

2. Copiar el archivo /etc/motd a un archivo llamado mensaje en el directorio prueba

```bash
cp /etc/motd prueba/mensaje
```
**Explicacion:**
    - ```cp```: Copia ficheros o carpetas 

3. Copiar mensaje en dir1, dir2 y dir3. 

```bash
cp -r prueba/mensaje prueba/dir1 prueba/dir2 prueba/dir3 
```
**Explicacion:**
    - ```cp``: Copia ficheros o carpetas el parametro **-r** es para hacerlo de manera recursiva

4. Comprobar el ejercicio anterior mediante un solo comando.
 
```bash
tree 
```
**Explicacion:**
    - ```tree```:Lista los directorios y ficheros en forma de arbol, mas visual

5. Copiar los archivos del directorio rc.d que se encuentra en /etc al directorio dir31

```bash
sudo cp -r /etc/rc.d/ dir3/dir31 
```

6. Copiar en el directorio dir311 los archivos de /bin que tengan una a como segunda letra y su nombre tenga cuatro letras.

```bash
cp /bin/?a?? dir3/dir31/dir311/ 
```

7. Copiar el directorio de otro usuario y sus subdirectorios debajo de dir11 (incluido el propio directorio).

```bash
sudo cp -a /home/$USER/dir_a_copiar /prueba/dir1/dir11/
```

8. Mover el directorio dir31 y sus subdirectorios debajo de dir2.

```bash 
mv dir3/dir31 dir2/ 
```
**Explicacion:**
    - ```mv```: Mueve archivos y directorios  

9. Borrar los archivos y directorios de dir1, incluido el propio directorio.

```bash
sudo rm -rf dir1/ 
```
**Explicacion:**
    - ```sudo```:Da permisos de ejecucion en modo superusuario 
    - ```rm```: Permite eliminar ficheros o directorios, con el paramentro **-r** lo hace de manera recursiva y con **-f** fuerza a eliminar 

10. Copiar al directorio dir312 los ficheros del directorio /dev que empiecen por t, acaben en una letra que vaya de la a a la b y tengan cinco letras en su nombre.

````bash
cp /dev/t???[a-b] dir312/
````
**Explicacion:**
    - ```cp```: Copia directorios y archivos 
    - **t??[a-b]**: Archivos que empiezen por *t*, la interrogacion marca que hay tantos caracteres ahi, *[a-b]* esto indica que termina en uno de esos caracteres **a**,**b**,**c**

11. Borrar los archivos de dir312 que no acaben en b y tengan una q como cuarta letra.

```bash 
rm dir312/???q*[!b]
```
**Explicacion:**
    - ```rm```:Borra archivos y directorios
    - **???q*[!b]**: *???*, nos indica que los tres primeros caracteres sean los que sean, el cuarto nos indica que es *q*, y despues con *[!b]* nos dice que el ultimo caracter no puede ser la letra **b**

12. Mover el directorio dir312 debajo de dir3.

```bash
mv dir2/dir31/dir312/ dir3/ 
```

13. Crear un enlace simbólico al directorio dir1 dentro del directorio dir3 llamado enlacedir1

```bash
ln -s dir1 dir3/enlacedir1
```

**Explicacion:**
    - ```ln```: Crea enlaces a archivos y directorios, con el parametro **-s** le indicamos que es simbolico

14. Posicionarse en dir3 y, empleando el enlace creado en el ejercicio anterior, crear el directorio nuevo1 dentro de dir1.

```bash
cd dir3/ && mkdir enlacedir1/nuevo1 
```
**Explicacion:**
    - ```&&```: Permite ejecutar un comando al finalizar el anterior

15. Utilizando el enlace creado copiar los archivos que empiecen por u del directorio /bin en directorio nuevo1.

```bash
cd dir3 && cp /bin/u* enlacedir1/nuevo1/
``` 
**Explicacion:**
    - ```cd```: Nos cambia de directorio
    - **'u*'**: Nos coje todos los ficheros y directorios que empiezen por **U**  

16. Borrar todos los archivos y directorios creados durante los ejercicios

```sudo rm -rf prueba/ ``` 

17. Listar todos los archivos del directorio etc que empiecen por t en orden inverso

```bash
ls -r /etc/t* 
```
**Explicacion:**
    - ```ls```: lista directorios y archivos, con el parametro **-r** lo hace en orden reverso
    - **'t*'**: nos indica los ficheros que empiezen por **t**

18. Listar todos los archivos del directorio dev que empiecen por tty y acaben en 1,2,3 ó 4.

```bash
ls /dev/tty[1-4]
```

**Explicacion:**
    -**tty[1-4]**:Los ficheros tty que acaben en los numeros etre 1 y 4

19. Listar todos los archivos del directorio etc que no empiecen por t. 

```bash
ls /etc/[!t]*
```
**Explicacion:**
    - **'[!t]*'**: Con el asterisco decimos que copie todos los fichero pero antes hemos indicado que no pueden empezar por t **[!t]** 

20. Crear el directorio dir2 y dir3 en el directorio PRUEBA ¿Cuáles son los actuales permisos del directorio dir2?
```bash 
mkdir prueba/dir2 prueba/dir3 
```

```bash
755
```
**Explicacion:**
    - ```ls -l```:Con este comando vemos los permisos de un fichero aunque es en notacion simbolica

21. Utilizando la notación simbólica (caracteres), eliminar todos los permisos de escritura (propietario, grupo, otros) del directorio dir2

```bash
chmod a-w dir2 
```
**Explicacion:**
    - ```chmod```: cambia los permisos de fichero y carpetas

22. Utilizando la notación octal, eliminar el permiso de lectura del directorio dir2, al resto de los usuarios.

```bash
chmod 771 dir2
```

23. ¿Cuáles son ahora los permisos asociados a dir2?

- Propietario: Lee, escribe y ejecuta (rwx).
- Grupo : Lee, escribe y ejecuta (rwx).
- Otros : Solo ejecuta (--x).

24. Crear bajo dir2, un directorio llamado dir2l 

``` bash
mkdir dir2/dir2l 
```

25. Concederse a sí mismo permiso de escritura en el directorio dir2 e intentar de nuevo el paso anterior.

```bash
chmod u+w dir2 
```

26. Cambiar el directorio actual al directorio dir3. Imprimir su trayectoria completa para verificar el cambio.

```bash
 cd dir3 && pwd 
 ```

**Explicacion:**
    - ```pwd```: Permite ver el directorio de trabajo actual

27. ¿Cuáles son los permisos asignados en su momento a este directorio?

28. Establecer mediante el comando umask (buscar este comando) los siguientes valores
por omisión: rwxr--r-- para los directorios y rw-r--r—para los archivos ordinarios. ¿Qué son los valores por omisión?

```bash
umask 022 
``` 
**Explicacion:**
    - ```umask```:Parecido a chmod pero con otra forma de expresion 

29. Crear cuatro nuevos directorios llamados dira, dirb, dirc, y dird bajo el directorio actual.

```bash 
mkdir dira dirb dirc dird 
``` 

30. Comprobar los permisos de acceso de los directorios recién creados para comprobar el funcionamiento del comando umask.

0022 

31. Crear el fichero uno. Quitarle todos los permisos de lectura. Comprobarlo. Intentar borrar dicho fichero.

``` Lo he borrado con total tranquilidad```

32. Quitarle todos los permisos de paso al directorio dir2 y otorgarle todos los demás.

```bash
chmod 666 dir2/
``` 

33. Crear en el directorio propio:

- El directorio carpeta1 con los tres permisos para el propietario, dentro de él fich1
con lectura y escritura para todos y fich2 con lectura y escritura parael
propietario y solo lectura para el resto.

```bash
mkdir carpeta1 && chmod u+rwx,go-rwx carpeta1 touch carpeta1/fich1 carpeta1/fich2 && chmod go+rwx fich1 && chmod u+rw,o-wx fich2  
```  

- El directorio carpeta2 con todos los permisos para el propietario y lectura y
ejecución para los del mismo grupo. Dentro file1 con lectura y escritura para el
propietario y los del grupo y file2 con los mismos para el propietario y solo
lectura para el grupo.

```bash
mkdir carpeta2 && cd carpeta2 && touch file1 file2 && chmod 750 file1 && chmod 710 file2
``` 

34. Desde otro usuario probar todas las operaciones que se pueden hacer en los ficheros y
directorios creados. 

- Carpeta 1: Error, permiso denegado 
- Carpeta 2: Se puede acceder 

35. Crear dos directorios llamados correo y fuentes debajo del directorio actual.
```bash
mkdir correo fuentes 
```

36. Posicionarse en el directorio fuentes y crear los directorios dir1, dir2, dir3.

```bash 
cd fuentes && mkdir dir1 dir2 dir3 
```  

37. Crear el directorio menus bajo correo sin moverse del directorio actual.

```bash
mkdir ../correo/menus 
``` 

38. Posicionarse en el directorio HOME. Borrar los directorios que cuelgan de fuentes que acaben en un número que no sea el 1.

```bash
cd && rm -r fuentes/dir[02-9] fuentes/dir?? 
``` 
**Explicacion:**
    - ```cd```:El comando cd sin nada nos mueve al home del usuario actual

39. Ver si existe el archivo tty2 en el directorio dev. En caso de que exista, ver su fecha de
creación o actualización.

```bash
ls -l --time=creation /dev/tty2 
```
**Explicacion:**
    - ```ls```:Lista directorios y ficheros, con el parametro **-l** lista todos y con **--time=creation** solicitamos cuando se creo

40. Ver los permisos que tienen los archivos que empiecen por tt del directorio /dev. 

```bash
ls -l /dev/tt* 
``` 

41. Visualizar la lista de todos los ficheros que pertenezcan a root.

```bash
find / -user root 
``` 
**Explicacion:**
    - ```find```: El comando se usa para buscar archivos y directorios, al pones la **/** decimos que busque desde el raiz, y con el parametro **-user** indicamos que usuario

42. Crear el directorio uno en el directorio HOME con permiso de escritura y paso para el
propietario, de lectura y paso para los usuarios de su mismo grupo y ningún permiso
para el resto de usuarios.

``` bash
mkdir uno && chmod u=wx,g=rx,o= ~/uno 
``` 

43. Crear el directorio uno1 dentro del directorio creado en el ejercicio anterior con todos lo
permisos para el usuario, ninguno para los usuarios del grupo y permiso de escritura
para el resto de usuarios.

```bash
cd uno && mkdir uno1 && chmod u=rwx,g=,o=w uno1 
``` 

44. Copiar todos los ficheros propiedad de un usuario conocido que acaben en un número
en el directorio menus.

```bash
find / -type f -user $USER -regex '.*[0-9]$' -exec cp {} /correo/menus/ \; 
```

45. Crea un archivo de tamaño 0

```bash 
touch archivo 
``` 
**Explicacion:**
    - ```touch```:Se usa para crear archivo vacios y cambiar marcas de tiempo de ficheros

46. Utilizando de entrada la información de los usuarios conectados al sistema, guardar,
ordenadas por el campo hora, las líneas correspondientes al usuario que se desee en el
archivo persona.

```who | grep $USER | sort -k4,4 -k5,5 > persona```

47. Crear el directorio carpeta debajo del directorio PRUEBA. Quitarle todos los permisos de lectura. A continuación, buscar todos los directorios que cuelguen del directorio propio y guardarlos en el archivo direc.

``` mkdir carpeta && chmod 333 carpeta && find . -type d > direc ``` 

48. Volver a realizar la segunda parte del ejercicio anterior, pero redireccionando los errores al fichero malos. Comprobar la información del fichero malos.

``` find . -type d 2> malos ``` 

49. Añadir al fichero direc la lista de todos los ficheros ordinarios que cuelguen de /etc

```find /etc -type f >> direc ``` 

50. Sacar por pantalla únicamente el tiempo (buscar comando time) que tarda en ejecutarse el comando who.

```time who``` 

51. Sacar por pantalla un listado completo (buscar comando ps) de los procesos que está realizando el usuario root.

``` sudo ps ``` 

52. Averiguar cuál es la actividad actual del sistema. Para ello visualice un listado completo del estado de todos los procesos que se están ejecutando en el sistema.

    1. Obtener un listado con los siguientes datos de los procesos de tu Shell actual.
    ``` ps aux ``` 
    2. Mostrar cuantos usuarios tiene registrados el sistema (el registro de usuarios
    está en el archivo /etc/passwd)
    ``` cat /etc/passwd ``` 
    3. Mostrar cuántos usuarios tiene registrados el sistema y que utilizan el intérprete bash (debe aparecer al final de la línea /bin/bash o similar)
    ``` cat /etc/passwd | grep "/bin/bash" ``` 
    4. Mostrar cuantos usuarios hay conectados
    ``` who ``` 

53. Extraer los nombres de usuario (primer campo) del sistema

```cat /etc/passwd | cut -d: -f1 ```  

54. Extraer los nombres de usuario y el shell que utilizan (último campo) 

``` cat /etc/passwd | cut -d: -f1,7``` 

55. Cambiar la fecha de creación de un archivo ya previamente creado 60. Monitorear la
ocupación de las particiones en los discos

``` touch -t 0102031445.34 direc ``` 

56. Monitorear laocupación de las particiones en los discos

``` df -h ``` 

61. ¿Cuál es el proceso que más carga el procesador?

``` top ``` o ``` htop  ``` 

62. ¿Cuántos procesos que empiecen por k están corriendo? 

``` ps -ef | grep '[kK]' | grep -v 'grep' ``` 

