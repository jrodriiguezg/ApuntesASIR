# Tema 3 - Administracion de usuarios y permisos 
## Administracion de usuarios 
Un sistema Linux puede ser administrador de tres formas diferentes: 

- **Interfaz grafica:** Es la forma mas facil y mas si vienes de sistemas Windows
- **Terminal:** Permite configurar el sistema de manera completa muchas opciones solo se pueden modificar usando herramientas de terminal
- **Ficheros de configuracion:** Modificar directamente archivos del sistema, hay que tener especial cuidado ya que podemos romper el sistema  

### Ficheros de inicio de sesion 

- ```/etc/issue``` Muestra el mensaje de bienvenida del sistema, aparece antes de iniciar sesion
- ```/etc/motd``` Mensaje cuando se inicia sesion mediante ssh o telnet
- ```/etc/profile``` Contiene configuraciones para todos los usuarios conectados al sistema, aqui se hace referencia al interprete de comandos 
- ```/etc/login.defs``` Establece las variables y ordenes que aefactan a todo los usuarios 

### Fichero de configuracion de usuario 

- ```.profile``` Se almacena en el homre del usuario. En él se configura el
entorno del usuario, se inicializan variable
- ```.bashrc``` Guarda la configuracion y scripts de usuario del interprete de comandos, aqui se guardan los alias 
- ```.bash_logout``` Procesa lo que se hace al cerrar sesion 

### Tipos de usuarios 

- **root:** Usuario administrador del sistema, no se aconseja usar la cuenta root para el uso comun y diario ya que puede romper el sistema 
- **Usuarios normales:** Son los usuarios con los que iniciamos sesion en el sistema, tiene funcionalidad limitada 
- **Usuarios de servicios:** No pueden iniciar sesion en el sistema, se usan por los servicios para gestionar ciertas tareas y privilegios 

### Usuario root 
Es el administrador del sistema, con UID 0 y GUID 0 tambien, con la orden ```sudo``` lanzamos comandos como administrador, las reglas de acceso los alias y opciones por defecto de sudo se almacenan en ``` /etc/sudoers``` 
El comando sudo se instala por defecto en ``` /etc/bin``` (la ruta puede variar entre sistemas o no existir en algunos casos).
Con ``` sudo -l ``` podemos ver cuales son los comandos que puede ejecutar el usuario 

### Creacion de usuarios y eliminacion de usuarios 
Para crear usuarios podemos usar tanto ```adduser | useradd``` ambos funcionan 
adduser, pregunta parametros y useradd no nos pregunta tanto 

Para eliminar usuarios usamos el comando ``` deluser -r [usuario]```  

### Gestion de grupos
Para crear un grupo usamos el comando ``` addgroup [nombre_grupo]```
Para añadir usuarios al grupo usamos ``` addgroup [nombre_grupo] [usuario]``` 
Para eliminar un grupo usamos ``` delgroup [nombre_grupo] ``` 

### Otros ficheros de configuracion 

#### /etc/passwd
Contiene todos los usuarios creados en el sistema, contiene lo siguiente:
nombre de usuario, contraseña cifrada, UID, GUID, datos personales, la shell por defecto 

#### /etc/shadow
Contiene las contraseñas encriptadas y datos de caducidad de la cuenta

#### /etc/group
Contiene los grupos del sistema, sus campos son: 
nombre del grupo, contraseña del grupo, GID, lista de usuarios 

#### /etc/gshadow 
Contiene una lista de usuarios que pertenecen a cada grupo 

#### /etc/login.defs
Establece las politicas y valores predeterminados de inicio de sesion, se pueden cambiar las siguientes cosas: 

- Validez de la contraseña 
- Opciones de seguridad
- Opciones del login: Intentos de contraseña, complejidad de la misma 

#### /etc/default/useradd 
Aqui se indica el directorio por defecto de los usuarios 


### Permisos 
