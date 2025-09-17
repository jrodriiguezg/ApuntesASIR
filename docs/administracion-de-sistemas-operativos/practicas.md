# Practica 1 - COMANDOS LINUX REPASO GENERAL

1. Crear los directorios dir1, dir2 y dir3 en un directorio PRUEBA. Dentro de dir1 crear el
directorio dir11. Dentro del directorio dir3 crear el directorio dir31. Dentro del directorio
dir31, crear los directorios dir311 y dir312.

```mkdir prueba/dir1 prueba/dir2 prueba/dir3 prueba/dir1/dir11 prueba/dir3/dir31 prueba/dir3/dir31/dir311 prueba/dir3/dir31/dir312``

2. Copiar el archivo /etc/motd a un archivo llamado mensaje en el directorio prueba

```cp /etc/motd prueba/mensaje```

3. Copiar mensaje en dir1, dir2 y dir3. 

```cp prueba/mensaje prueba/dir1 prueba/dir2 prueba/dir3 ```

4. Comprobar el ejercicio anterior mediante un solo comando.
 
```tree ```

5. Copiar los archivos del directorio rc.d que se encuentra en /etc al directorio dir31

``` sudo cp -r /etc/rc.d/ dir3/dir31 ```

6. Copiar en el directorio dir311 los archivos de /bin que tengan una a como segunda letra y su nombre tenga cuatro letras.

``` cp /bin/?a?? dir3/dir31/dir311/ ```

7. Copiar el directorio de otro usuario y sus subdirectorios debajo de dir11 (incluido el propio directorio).

```sudo cp -a /home/$USER/dir_a_copiar /prueba/dir1/dir11/```

8. Mover el directorio dir31 y sus subdirectorios debajo de dir2.

``` mv dir3/dir31 dir2/ ```

9. Borrar los archivos y directorios de dir1, incluido el propio directorio.

``` sudo rm -rf dir1/ ```

10. Copiar al directorio dir312 los ficheros del directorio /dev que empiecen por t, acaben en
una letra que vaya de la a a la b y tengan cinco letras en su nombre.

````cp /dev/t??[a-b] dir312/````

11. Borrar los archivos de dir312 que no acaben en b y tengan una q como cuarta letra.

```rm dir312/???q*[!b]```

12. Mover el directorio dir312 debajo de dir3.

```mv dir312 dir3/```

13. Crear un enlace simbólico al directorio dir1 dentro del directorio dir3 llamado enlacedir1

```ln -s dir1 dir3/enlacedir1```

14. Posicionarse en dir3 y, empleando el enlace creado en el ejercicio anterior, crear el directorio nuevo1 dentro de dir1.

```cd dir3 && mkdir enlacedir1/nuevo1 ```

15. Utilizando el enlace creado copiar los archivos que empiecen por u del directorio /bin en directorio nuevo1.

```cd dir3 && cp /bin/u* enlacedir1/nuevo1/``` 

16. Borrar todos los archivos y directorios creados durante los ejercicios

```sudo rm -rf prueba/ ``` 

17. Listar todos los archivos del directorio etc que empiecen por t en orden inverso

```ls -r /etc/t* ```

18. Listar todos los archivos del directorio dev que empiecen por tty y acaben en 1,2,3 ó 4.

```ls /dev/tty[1-4]```

19. Listar todos los archivos del directorio etc que no empiecen por t. 

```ls /etc/[!t]*```

20. Crear el directorio dir2 y dir3 en el directorio PRUEBA ¿Cuáles son los actuales permisos del directorio dir2?
``` mkdir prueba/dir2 prueba/dir3 ```

```775```

21. Utilizando la notación simbólica (caracteres), eliminar todos los permisos de escritura (propietario, grupo, otros) del directorio dir2

``` chmod a-w dir2 ```

22. Utilizando la notación octal, eliminar el permiso de lectura del directorio dir2, al resto de los usuarios.

```chmod 771 dir2```

23. ¿Cuáles son ahora los permisos asociados a dir2?

- Propietario: Lee, escribe y ejecuta (rwx).
- Grupo : Lee, escribe y ejecuta (rwx).
- Otros : Solo ejecuta (--x).

24. Crear bajo dir2, un directorio llamado dir2l 

``` mkdir dir2/dir2l ```

25. Concederse a sí mismo permiso de escritura en el directorio dir2 e intentar de nuevo el paso anterior.

``` chmod u+w dir2 ```

26. Cambiar el directorio actual al directorio dir3. Imprimir su trayectoria completa para verificar el cambio.

``` cd dir3 && pwd ```

27. ¿Cuáles son los permisos asignados en su momento a este directorio?

28. Establecer mediante el comando umask (buscar este comando) los siguientes valores
por omisión: rwxr--r-- para los directorios y rw-r--r—para los archivos ordinarios. ¿Qué son los valores por omisión?

``` umask 022 ``` 

29. Crear cuatro nuevos directorios llamados dira, dirb, dirc, y dird bajo el directorio actual.

``` mkdir dira dirb dirc dird ``` 

30. 