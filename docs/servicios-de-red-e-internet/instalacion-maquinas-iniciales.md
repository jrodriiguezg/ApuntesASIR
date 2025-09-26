# Instalación Windows Server 2022 
Yo voy a usar Libvirt en vez de VMware, ya que en Fedora Silverblue, que es lo que uso, no se puede instalar otra cosa. Debido a que es un sistema inmutable y las opciones de virtualizacion solo son o QEMU/KVM o podman/docker 

Esta primera captura muestra la pantalla inicial de Libvirt (que es una interfaz gráfica para QEMU/KVM). En la esquina superior izquierda está el botón para crear una máquina virtual.

![InicioDeLibvirt](images/Wserver/1.png)

Ahora nos pregunta desde dónde queremos instalar nuestra máquina virtual. Seleccionamos medio local.

![PantallaCreacionMaquina](images/Wserver/2.png)


La siguiente imagen nos muestra el selector de medios de instalación. Aquí podemos elegir el sistema operativo a instalar y la ISO. Para elegir la ISO, debemos pulsar en explorar y se abrirá la ventana siguiente.

![Almacenamiento](images/Wserver/4antesde3.png)

Se nos abre la siguiente ventana y tenemos que seleccionar **Explorar localmente** para buscar la ISO en nuestro sistema.

![SeleccionDeISO](images/Wserver/3.png)

En el siguiente paso se configura la memoria RAM del sistema. En este caso, vamos a definir 4 GB (4096 MB).
![RAM](images/Wserver/5.png)

Ahora creamos el disco duro, en este caso de 60 GB, y pulsamos adelante.
![CreacionDiscoDuro](images/Wserver/6.png)

Aquí finalmente vemos cómo quedaría nuestra instalación, con un resumen de todo. Pulsamos finalizar.

![InstalacionFinal](images/Wserver/7.png)

Ahora iniciara el instalador de Windows Server

![WindowsIniciando](images/Wserver/8.png)

Esta primera pantalla nos pedirá que introduzcamos el idioma del sistema (aunque la ISO es la versión española y solo nos deja español).

![SeleccionDeIdioma](images/Wserver/9.png)

En el siguiente paso solo debemos pulsar en **Instalar**

![PulsarInstalar](images/Wserver/10.png)

Y comenzará a cargar el instalador.

![Instalador](images/Wserver/11.png)

Esta primera pantalla nos pregunta qué tipo de versión de Windows Server vamos a usar. Tenemos 4 versiones diferentes: dos para servidor y dos para datacenter, y luego una versión en modo escritorio y otra en modo gráfico. Nosotros cogemos la segunda opción: modo servidor con interfaz gráfica.

![SelectorVersion](images/Wserver/12.png)

En la siguiente ventana nos pregunta si queremos aceptar el EULA (es obligatorio).

![AceptarEULA](images/Wserver/13.png)

Ahora nos preguntará el tipo de instalación que queremos: si actualizar una versión de Windows anterior o una instalación avanzada desde cero. Seleccionamos esta última opción.

![TipoInstalacion](images/Wserver/14.png)

El disco duro virtual es de 60 GB y queremos tener una partición de 50 GB y otra de 10 GB aproximadamente. Para ello, pulsamos en el disco a particionar y después en **Nuevo**.

![Particionado](images/Wserver/15.png)

Ahora definimos el tamaño del disco. Como queremos una partición de 50 GB y otra de 10 GB, en vez de 61000 MB, ponemos 51000 MB y así haría dos particiones diferentes. Pulsamos en **Aplicar**.

![Particionado2](images/Wserver/16.png)

Ahora seleccionamos la partición de 50 GB para instalar el sistema y pulsamos en **Instalar**.

![Particionado3](images/Wserver/17.png)

Nos saltará el siguiente aviso, informando de que faltan particiones del sistema. Al pulsar en **Aceptar**, las creará de manera automática.

![Particionado4](images/Wserver/19antesde17.png)

Iniciará la instalación de Windows Server, se reiniciará automáticamente y nos saldrá esta pantalla, en la que introduciremos la contraseña. Después, pulsaremos **Finalizar**.

![Contraseña](images/Wserver/20.png)

Al fin, Windows Server iniciará.

![Iniciando](images/Wserver/21.png)

Nos saltará el aviso de la red local. Pulsamos en **Sí**.

![Iniciando1](images/Wserver/22.png)

## Activación de usuario administrador
Nos vamos al lanzador de programas de Windows y buscamos el simbolo del sistema (CMD), pulsamos click derecho y lo abrimos como administrador

![CMD](images/Wserver/23.png)

Ahora escribimos el siguiente comando ```net user administrador /active:yes``` y pulsamos Intro.

![CMD_comando](images/Wserver/24.png)

Ahora vamos a comprobar que se ha habilitado el usuario administrador de manera correcta. Para ello, abrimos el cuadro de ejecutar, bien buscándolo en la barra de búsqueda o pulsando las teclas **Windows (Super) + R**.

![Abrir_ejecutar](images/Wserver/25.png)

En el cuadro de ejecutar escribimos ```secpol.msc``` y pulsamos Intro.

![secpol.msg](images/Wserver/27.png)

Se nos abrirá el panel de directivas de seguridad local. Aquí debemos buscar en Directivas locales > Opciones de seguridad > y dentro de opciones de seguridad buscamos **Cuentas: Estado de la cuenta de administrador**. Debe poner Habilitada.

![Administrador_habilitado](images/Wserver/29.png)

## Instalacion de las Spice Tools (Guest Additinos de Libvirt)

Al igual que en virtualbox o vmware que se instalan los extras en la maquina virtualizada para agregar soporte de graficos, o arrastrar y soltar entre otros en libvirt tambien se instalan estas aunque no es tan simple como en las dos primeras opciones que es pulsar un boton 
En el caso de libvirt debemos irnos a la pagina de descarga de las [SpiceTools](https://www.spice-space.org/download.html)

En la página hay descargas para diferentes sistemas operativos. Para Windows hay que buscar la opción que diga **Windows Binaries** y pulsar el primer enlace.

![Spice_tools](images/Wserver/30.png)

Al ser software de código abierto no está firmado (ya que esto cuesta dinero), por lo que nos saltará el siguiente aviso de Smart Screen. Solo debemos pulsar en ejecutar.

![Smart_screen](images/Wserver/31.png)

La instalación comenzará.

![Instalacion](images/Wserver/32.png)

Aceptamos el acuerdo de licencia.

![Instalacion2](images/Wserver/33.png)

Y después de un rato se finalizará la instalación.

![InstalacionFin](images/Wserver/35.png)


## Configuración del navegador web
Como navegador, yo he elegido Firefox, ya que es el que uso a diario y el que menos recursos consume.

![Firefox](images/Wserver/37.png)

Para configurar la navegación privada de manera predeterminada en Firefox hay que hacer los siguientes pasos:
Abrimos el navegador y nos desplazamos al desplegable de la esquina superior derecha, como se ve en la imagen. Ahí pulsamos en Ajustes.

![Firefox_ajustes](images/Wserver/39antes.png)

Una vez en Ajustes, en el buscador superior buscamos **Historial**. En la primera opción que señala **Firefox podrá:**, pulsamos y se abrirá un desplegable en el que seleccionaremos la última opción: **Usar una configuración personalizada para el historial**.

![historial](images/Wserver/40.png)

Después debemos marcar la casilla que dice **Usar siempre el modo de navegación privada**. Después de esto, todos los datos de la sesión de búsqueda se borrarán al salir.

![historial2](images/Wserver/39.png)

## Configuracion contraseñas y nombre del equipo 

Ahora vamos a desabilitar las contraseñas seguras y el tiempo que tardan en expirar en el sistema 

Para cambiar estos ajustes nos vamos al Panel de administracion del servidor > Herramientas > Directivas de Seguridad Local
![directivasseguridad](images/Wserver/4142.png)

Una vez dentro de **Directivas de seguridad local**, nos desplazamos a Directiva de cuenta > Directiva de contraseña y pulsamos en **La contraseña debe cumplir los requisitos de complejidad**

![directivasseguridad_ventana](images/Wserver/41.png)

Y ahora pulsamos en deshabilitado, despues en aplicar o aceptar. 

![Deshabilitar](images/Wserver/42.png)

Ahora cambiaremos la vigencia maxima de la contraseña de 45 dias a 300 

![300](images/Wserver/43.png)

Al final debe quedar asi

![Final](images/Wserver/44.png)

Ahora vamos a cambiar el periodo de actualizacion del servidor de 10 minutos a 1 minuto, para ello pulsamos en Administrar > Propiedades del administrador del servidor y en la primera opcion cambiamos el tiempo de 10 a 1  
Despues pulsamos **Agregar**

![Final](images/Wserver/45.png)

Ahora cambiaremos el nombre del equipo, para ello nos desplazamos a Administrador de archivos > Este equipo > Click derecho, propiedades > y bajamos hasta ver la opcion de **Cambiar nombre del equipo**

![NombreEquipo](images/Wserver/46.png)

Al pulsar en **Cambiar nombre de equipo** se nos abre la siguiente ventana en la que introduciremos **SERVIDORW25XX**, despues pulsamos siguiente y **reiniciar mas tarde**

![NombreEquipo](images/Wserver/47.png)
![Reinicio](images/Wserver/48.png)

## Creacion de Redes Privadas (LAN) en Libvirt (QEMU)
Para crear una red privada en QEMU debemos primero crear la red mediante un fichero **.xml**, despues con ese fichero levantar la red y activarla, y una vez todo esto ya nos aparecera en LibVirt

Desde una terminal o con el editor de texto, creamos un archivo con el nombre que sea pero terminacion **.xml** y ponemos el siguiente contenido 

```
<network> 
    <name>nombre_de_la_red</name>
</network> 
```

![red_windows.xml](images/Wserver/49.png)

Despues, ponemos los siguientes comandos para levantar la red privada 

- ```sudo virh net-define [fichero.xml]``` Este comando levanta la red
- ```sudo virsh net-start [nombre_red]``` Este comando inicia la red 
- ```sudo virsh net-autostart [nombre_red]``` Este comando inicia la red en el inicio del sistema 

Si qusieramos eliminar una red 

- ```sudo virsh net-undefine [nombre_red]``` Para desactivarla 
- ```sudo virsh net-destroy [nombre_red] ``` Para borrarla 

![Inicio_red](images/Wserver/50.png)

Para agregar hardware, pulsamos la bombilla al lado del icono del monitor, despues pulsamos en **Añadir hardware**

![Inicio_red](images/Wserver/55.png)

Despues seleccionamos el tipo de hardware, en este caso red, y vemos que nos sale **Red Virtual "red-windows"**, seleccionamos y pulsamos finalizar 

![Inicio_red](images/Wserver/51.png)

Ahora en la maquina windows server, con la LAN conectada, nos vamos al **Centro de redes y recursos compartidos** seleccionamos nuestro adaptador de red asignado a LAN, pulsamos en click derecho > Propiedades, despues **Pulsamos protocolo de internet version 4**.
Y establecemos la direccion IP de manera manual en este caso sera la **192.168.10.1**
Al acabar pulsamos Aceptar 

![Configurar_IP](images/Wserver/52.png)

Les he cambiado el nombre, por que ahun que yo las indentifico asi se ve mas facil 

![Redes](images/Wserver/53.png)

Desde una **CMD** podemos ver los ajustes de red y la configuracion haciendo ```ipconfig /all```

![ipconfig](images/Wserver/54.png)

## Activacion
Desde un **CMD** y con la red NAT desactivada (sin acceso a internet), introducimos el siguiente comando para activar el windows Server y quitar la marca de agua de la esquina 
´´´ dism /online /set-edition:serverStandard /productkey:VDYBN-27WPP-V4HQT-9VMD4-VMK7H /accepteula ``` 

![Activar](images/Wserver/56.png)

Al finalizar el proceso, nos preguntara si queremos reinciar, ponemos una **Y** para reiniciar 

![Reiniciar](images/Wserver/57.png)

## Configuracion de la contraseña en el usuario Administrador 

Para ello abrimos el Panel de control 

![Panel_control](images/Wserver/58.png)

Nos desplazamos a cuentas de usuario 

![Cuentas_de_usuario](images/Wserver/59.png)

Y ahi pulsamos en administrar otra cuenta

![Administrar_otra_cuenta](images/Wserver/60.png)

Una vez dentro hacemos doble clic en el usuario **Administrador**

![Usuario_administrador](images/Wserver/61.png)

Y pulsamos en cambiar la contraseña 

![Cambiar_Contraseña](images/Wserver/62.png)


Y establecemos la contraseña 

![Nueva_contraseña](images/Wserver/63.png)

Despues reiniciamos 

## Creacion de una snapshoot 

Ahora vamos a crear la snapshoot de la maquina cero, con lo basico ya creado, como forma de copia de seguridad por si algo sale mal, para ello en libvirt pulsamos vista > Instantaneas 

![Instantanea](images/Wserver/64.png)

Abrimos el gestor de instantaneas y pulsamos en el **+** de la parte inferior 

![Crear](images/Wserver/65.png)

Se nos abrira la siguiente ventana, establecemos el nombre el tipo de instantanea y la descripcion 

![Crear2](images/Wserver/66.png)


# Instalacion Windows 10
En clase se ha visto como hacer lo que se conoce como instalacion desatendida una opcion que esta en VirtualBox o Vmware pero en Libvirt no existe, por lo que yo he documentado una instalacion normal de Windows 10 

Seleccionamos medio de instalacion local y pulsamos adelante

![Paso1](images/w10/1.png)

Seleccionamos el archivo ISO, para ello pulsamos en Explorar 

![Paso2](images/w10/2.png)

Despues pulsamos en explorar localmente y buscamos nuestra imagen .iso 

![Paso3](images/w10/3.png)
![Paso4](images/w10/4.png)

Despues pulsamos siguiente 

![Paso5](images/w10/5.png)

Ahora establecemos la cantidad de RAM y el numero de CPUs a usar, lo he dejado por defecto y pulsamos adelante

![Paso6](images/w10/6.png)

Ahora definimos el tamaño del disco duro, por defecto lo da en 20Gb lo he subido a 60Gb 

![Paso7](images/w10/7.png)

En este ultimo paso definiremos el nombre de la maquina virtual , y podremos ver un resumen simplificado de nuestra maquina virtual, pulsamos en finalizar

![Paso8](images/w10/8.png)

Ahora comenzara la instalacion de Windows 10 (he saltado pasos por que es muy parecida a windows server, como las preguntas de recoleccion de datos, que he pulsado **No** en todo)

![Paso9](images/w10/9.png)

Pulsamos **Instalar ahora** para instalar Windows 10 

![Paso10](images/w10/10.png)

En el siguiente paso nos pedira clave del producto, no tengo clave entonces pulso en **No tengo clave de producto**

![Paso11](images/w10/11.png)

Ahora nos pedira la version de Windows, nos desplazamos en la lista y seleccionamos **Windows 10 Pro** y pulsamos siguiente

![Paso12](images/w10/12.png)

En el siguiente paso seleccionamos la segunda opcion **Instalar solo windows (avanzado)**

![Paso13](images/w10/13.png)

Ahora nos pasara al particionado del disco, donde seleccionaremos el disco que tenemos, y pulsaremos en **Nuevo**, nos pedira el espacio del disco, cogemos todos y pulsamos en **Aplicar**

![Paso14](images/w10/14.png)

El particionado se deberia ver algo asi 

![Paso15](images/w10/15.png)

Pulsamos siguiente y comenzara la instalacion 

![Paso16](images/w10/16.png)

 Al acabar Windows se reiniciara, y empezara la configuracion inicial del sistema, los primeros pasos son seleccion de idioma, distribucion de teclado... 

 ![Paso17](images/w10/17.png)

 Despues de un par de pasos molestos, nos perdira el nombre de la cuenta, le he puesto **Usuario**

 ![Paso18](images/w10/18.png)

 De contraseña no le he puesto ninguna 

 ![Paso19](images/w10/19.png)

Ahora nos empezaran a saltar las opciones de privacidad y cortana, pulsamos **NO** en todo

![Paso20](images/w10/20.png)

Despues de un rato se instalara 

![Paso21](images/w10/22.png)

## Activacion de Windows y cuenta de administrador 
Ahora vamos a activar windows mediante el CMD, para ello nos vamos al buscador de programas de windows, escribimos CMD y pulsamos clic derecho **Ejecutar como administrador**

![Paso23](images/w10/23.png)

Introducimos el siguiente comando ```SLMGR /IPK 6TP4R-GNPTD-KYYHQ-7B7DP-J447Y``` y pulsamos enter y luego **Aceptar**

![Paso24](images/w10/24.png)

Ahora ponemos el siguiente comando ```SLMGR /SKMS KMS.DIGIBOY.IR ``` pulsamos enter y aceptar 

![Paso25](images/w10/25.png)

Para finalizar ponemos el siguiente comando ```SLMGR /ATO ``` pulsamos enter y aceptar 

![Paso26](images/w10/26.png)

Ahora activaremos la cuenta de Administrador, para ello escribimos ```NET USER ADMINISTRADOR /ACTIVE:YES ``` 

![Paso27](images/w10/27.png)

Desde las directivas de seguridad local, podemos ver que la cuenta de administrador esta activada: 

![Paso28](images/w10/28.png)

## Instalacion de la red Virtual 
Como ya esta creada de la instalacion de Windows Server no es neecsario crearla de nuevo, los pasos son los mismos que anteriormente, añadimos un nuevo dispositivo hardware > elegimos tarjeta de red y en el tipo de red elegimos **red virtual windows**

![Paso29](images/w10/29.png)

Aqui vemos que tenemos dos tarjetas de red

![Paso30](images/w10/30.png)

## Instalacion de las SPICE Guest Tools y el navegador
Los pasos son los mismso que la instalacion anterior, nos las descargamos desde este [enlace](https://www.spice-space.org/download.html) y las instalamos 

![Paso31](images/w10/31.png)

Ahora instalaremos el navegador web, yo usare firefox, en mi caso tengo el ejecutable en mi equipo anfitrion y al instalar las Guest Tools lo paso con el arrastrar y soltar

![Paso32](images/w10/32.png)

## Cambio del nombre del equipo
Para cambiar el nombre del equipos, nos vamos al administrador de archivos y en **Mi equipo** hacemos clic derecho > Propiedades, se nos abrira esta ventana 
Pulsaremos en **Cambiar configuracion**

![Paso33](images/w10/33.png)

Despues pulsamos en **Cambiar** y donde pone nombre del equipo, ponemos el nuevo nombre, despues pulsamos en **Aceptar**

![Paso34](images/w10/34.png)

## Configuracion de la red
Cambiamos el nombre de las tarjetas de red para reconocerlas mas facilmente como se ve en la imagen y en la tarjeta de red NAT, le pulsamos clic derecho > Propiedades > **Protocolo de internet version 4**, dejamos todo tal cual esta 
Hacemos los mismos pasos en la red LAN, pero ahora estableceremos la direccion IP de manera manual, en este caso este cliente tendra la direccion **192.168.10.10**
Al acabar pulsamos en **Aceptar**

![Paso35_1](images/w10/35.png)

![Paso35](images/w10/36.png)

## Desactivacion de las actualizaciones firewall y establecer contraseña al administrador 
Para desactivar las actualziaciones, nos vamos a configuracion > Actualizaciones y serguridad > Opciones avanzadas y desactivamos todas las opciones 

![Paso36](images/w10/37.png)

Para desactivar el firewall seguimos los mismo pasos que en Windows server 

![Paso37](images/w10/38.png)

Para establecer la contraseña al administrador seguimos los mismos pasos que en windows server 

![Contraseña](images/w10/40.png)

## Comprobacion del funcionamiento de la red LAN entre maquinas 
Mediante el uso de la herramienta ping, hacemos ping del servidor al cliente y del cliente al servidor 

Esta primera captura muestra el ping desde el cliente hacia el servidor (192.168.10.1)

![Ping_desdeCliente](images/w10/39_desdeCliente.png)

Esta siguiente captura muestra el ping del servidor al cliente (192.168.10.10)

![Ping_desdeServidor](images/w10/39_desdeServidor.png)

## Instalacion de Active directory en el Windows Server y configuracion
Para instalar el Active directory (controlador de dominio) en windows server, nos vamos al administrador del servidor > Administrar > Instalar Roles y caracteristicas 

![Paso38](images/Wserver/68.png)

Se nos abre esta ventana con un resumen de lo que se va a hacer, pulsamos **Siguiente**

![Paso39](images/Wserver/69.png)

Seleccionamos **Instalacion basada en roles y caracteristicas** y pulsamos siguiente 

![Paso40](images/Wserver/70.png)

Seleccionamos el servidor de destino de la instalacion, solo hay uno por lo que no hay problemas y pulsamos siguiente 

![Paso41](images/Wserver/71.png)

Ahora en la lista debemos buscar los **Servicios de dominio de active directory** los pulsamos

![Paso42](images/Wserver/72.png)
![Paso43](images/Wserver/73.png)
![Paso44](images/Wserver/74.png)

En la siguiente opcion nos habla de las caracteristicas, lo dejamos por defecto y pulsamos **Siguiente**

![Paso45](images/Wserver/75.png)

Con la opcion de azure saltamos, pulsando **siguiente**

![Paso46](images/Wserver/76.png)

Ahora pulsaremos en **Instalar**

![Paso47](images/Wserver/77.png)
![Paso48](images/Wserver/78.png)

Nos saltara el aviso de promocionar el equipo a **Controlador de dominio**, le pulsamos 

![Paso49](images/Wserver/79.png)

Se nos abrira una ventana nueva, marcamos la casilla de **agregar un nuevo bosque**, nos pedira que especifiquemos el nombre del dominio raiz, importante poner el final del dominio es decir **.es**, **.edu**, etc. Si no nos saldra el error que vemos en la imagen en rojo.

![Paso50](images/Wserver/80.png)

En la imagen siguiente vemos como al poner el dominio **dominiow25jrrg.edu** ya nos permite continuar 

![Paso51](images/Wserver/81.png)

En el siguiente paso, el nivel funcional lo dejamos por defecto y la contraseña le ponemos **Administardor1** y pulsamos siguiente 

![Paso52](images/Wserver/82.png)

Ahora nos preguntara si queremos crear una delegacion DNS, no marcamos nada y pulsamos **Siguiente**

![Paso53](images/Wserver/83.png)

El nombre de NetBIOS no lo rellena de manera autoamtica, por lo que solo debemos pulsar **Siguiente**

![Paso54](images/Wserver/84.png)

Y las rutas de los archivos dejamos las por defecto, pulsamos **Siguiente**

![Paso55](images/Wserver/85.png)

Ahora nos mostrara las configuraciones que se van a hacer, pulsamos **Siguiente**

![Pas56](images/Wserver/86.png)

Para finalizar, si todo ha salido bien, nos aparecera arriba el aviso (los avisos en amarillo son solo advertencias).

![Paso57](images/Wserver/87.png)

El servidor se reiniciara para completar la instalacion 

![Paso58](images/Wserver/88.png)

Y al volver a arrancar veremos como el inicio de sesion ha cambiado 

![Paso59](images/Wserver/89.png)

Ahora en el servidor quitaremos el firewall 

![Paso60](images/Wserver/92antesde91.png)

Y en el cliente pondremos la direccion del servidor como DNS primario, 

![Paso61](images/Wserver/91.png)

Ahora vamos a unir el cliente al dominio, para ello nos vamos al mismo sitio en el que cambiamos el nombre del equipo, pero esta vez, nos vamos a la seccion de **Miembro de** y seleccionamos **Dominio** despues pulsamos **Aceptar**

![Paso62](images/Wserver/93.png)

Nos pedira las contraseñas del usuario Administrador del servidor 

![Paso63](images/Wserver/94.png)

Despues nos avisara que el cliente se ha unido al dominio correctamente y reiniciamos

![Paso64](images/Wserver/95.png)

Al reiniciar nos vamos a iniciar sesion con otro usuario, sabemos que estamos haciendolo bien, por que nos dice **Iniciar sesion en (y el nomrbe del cliente)**

![Paso65](images/Wserver/96.png)

Ahora en el servidor y desde el administardor del servidor, nos vamos a herramientas > **Usuarios y equipos de active directory**

![Paso66](images/Wserver/97.png)

Podemos ver que el cliente esta unido en el panel de **Usuarios y equipos de active directory**

![Paso67](images/Wserver/98.png)

El firewall se reactivara al reinciar, por lo que lo desactivamos, tanto en el cliente como en el servidor

![Paso68](images/Wserver/99.png)
![Paso68](images/Wserver/100.png)

En el cliente podemos verificar que se ha unido de manera correcta al dominio, desde el panel de Sistema y seguridad > Sistema 

![Paso69](images/Wserver/101.png)

Ahora deberemos desactivar la compelejidad de la contraseña ya que a mi se me ha vuelto a activar, para ello nos vamos a Administrar > Administrador de directivas de grupo > Bosque > Dominios > nuestro dominio > **Default domain policy** y hacemos clic derecho > editar, se nos abrira el **Editor de administracion de directivas de grupo** y nos vamos a Configuracion de equipo > Directivas > Configuracion de Windows > Directivas de cuenta > Directivas de contraseña y verificamos si el apartado de **La contraseña debe cumplir los requisitos de complejidad** esta en **desabilitada**

![Paso70](images/Wserver/102.png)

Ahora en **Servidor Local**, pulsamos en **Seguridad mejorada de IE** y desactivamos todo 

![Paso71](images/Wserver/103.png)


# Instalacion de Ubuntu 
## Creacion de la maquina virtual
Ahora vamos a instalar Ubuntu, no especifico si servidor o cliente ya que el mismo vale para ambos instalaremos uno y lo clonaremos, en clase se ha hecho una instalacion desetentidad pero yo no puedo hacerla 

Le damos a nueva maquina virtual, **medio de instalacion local** y adelante
![Paso72](images/ubuntu/1.png)

Seleccinamos la ISO y pulsamos adelante 

![Paso73](images/ubuntu/2.png)

En la configuracion de RAM y CPU, lo dejamos por defecto 

![Paso74](images/ubuntu/3.png)

El disco por defecto nos dice 20Gb yo lo he puesto en 60Gb y pulsamos adelante 

![Paso75](images/ubuntu/4.png)

He puesto cliente en el nombre pero este es el server, pero como son iguales no pasa nada, luego lo cambio 

![Paso76](images/ubuntu/5.png)

## Instalacion de Ubuntu en la maquina virtual

Se iniciara la maquina y nos pedira el idioma del instalador, con el teclado se selecciona **Español**

![Paso77](images/ubuntu/6.png)

En el selector del modo de instalacion, elegimos **Instalar ubuntu** 

![Paso78](images/ubuntu/7.png)

Se abrira el instalador y seleccionamos el idioma **Español** y pulsamos continuar 

![Paso79](images/ubuntu/8.png)

Ahora la disposicion de teclado dejamos por defecto y pulsamos continuar 

![Paso80](images/ubuntu/9.png)

Ahora en el tipo de instalacion, selecciono **Instalacion minima** para que menos cosas 

![Paso81](images/ubuntu/10.png)

No voy a hacer particionado por lo que elijo la primera opcion y que lo haga automatico 

![Paso82](images/ubuntu/11.png)

En la ubicacion, lo dejo por defecto 

![Paso83](images/ubuntu/12.png)

Ahora configuramos lass opciones del usuario, me he equivocado en el nombre de usuario, he puesto administardor en vez de usuario, ahora si he puesto bien que esto es el servidor 

![Paso84](images/ubuntu/13.png)

Ahora comenzara la instalacion y le dejamos su tiempo 

![Paso85](images/ubuntu/14.png)

Al finalizar los avisara de que reiniciemos, le decimos que si 

![Paso86](images/ubuntu/15.png)

Le he cambiado el nombre a la maquina 

![Paso87](images/ubuntu/16.png)

## Configuracion de Ubuntu

Iniciamos la maquina 

![Paso88](images/ubuntu/17.png)

Ahora todas estas preguntas, vamos rapido con ellas, reportes de errores le decimos que no, livepatch que no tampoco y servicios de ubicacion, tampoco los queremos 

![Paso89](images/ubuntu/18.png)
![Paso90](images/ubuntu/19.png)
![Paso91](images/ubuntu/20.png)
![Paso92](images/ubuntu/21.png)

Se iniciara el escritorio de ubuntu 

![Paso93](images/ubuntu/22.png)

Aprovechando el tiempo le he cambiado el nombre al usuario desde la configuracion 

![Paso94](images/ubuntu/23.png)

Ahora cambiamos el inicio de sesion e iniciamos sesion con **Administrador**

![Paso95](images/ubuntu/24.png)

Actualizaremos los repositorios y el sistema todo en una linea con el comando 
```bash 
sudo apt update && sudo apt upgrade 
```

![Paso96](images/ubuntu/25.png)
![Paso97](images/ubuntu/26.png)

Ahora accederemos con el usuario **root** 

![Paso98](images/ubuntu/28.png)

Le establecemos la contraseña al usuario root

![Paso99](images/ubuntu/29.png)

Ahora modificamos el fichero ```/etc/gdm3/custom.conf/``` para permitir el inicio de sesion con el usuario **root** y agregamos la linea ```AllowRoot = true``` 

![Paso100](images/ubuntu/30.png)
![Paso101](images/ubuntu/31.png)

Ahora modificamos otro fichero para lo mismo que antes, en este caso solo agregamos un **#**

![Paso102](images/ubuntu/32.png)
![Paso103](images/ubuntu/33.png)

Aprovecho que la clase va algo mas lenta e instalo las guest-adittions y fish que es un bash con esteroides 

![Paso104](images/ubuntu/34.png)

Ahora inciamos sesion con el usuario **root**

![Paso105](images/ubuntu/35.png)

Volviendo a aprovechar que la clase va lenta  le cambiamos bash por fish con el siguiente comando, las ventajas de fish es que mete colores, recuerda comandos ya usados y autocompleta con mas facilidad que bash, usamos el siguiente comando 
```bash 
chsh -s /usr/bin/fish
```

![Paso106](images/ubuntu/37.png)

Aqui vemos un poco fish, que nos permite autocompletar comandos anteriores, y al tabular aparte de mostarnos los comandos posibles nos pone que hacen (en ingles)

![Paso107](images/ubuntu/38.png)


Ahora configuraremos la Red LAN, anteriormente he explicado como se crea una red virtual en QEMU por lo que no repito pasos, aqui vemos como la red **red-linux** esta creada y la estoy añadiendiendo como red LAN
![Paso110](images/ubuntu/41.png)

Mi red se llama diferente dedbido a los drivers que usa la maquina virtual, al ser diferentes a los de VMware se llaman diferentes, mi red LAN es **enp7s0**

![Paso111](images/ubuntu/42.png)

Pulsamos en el engranaje para abrir la configuracion, y le cambiamos el nombre y pones la direccion de red como manual y con la siguiente IP **192.168.20.1**

![Paso112](images/ubuntu/43.png)
![Paso113](images/ubuntu/45.png)

Y ahora le cambiamos el nombre a la NAT 

![Paso114](images/ubuntu/44.png)

Ahora instalamos las net-tools que son necesarias para usar el comando ```ifconfig``` 
![Paso115](images/ubuntu/46.png)
![Paso115.1](images/ubuntu/47.png)

## Clonacion de la maquina virtual Ubuntu Servidor para hacer un cliente 

Seleccionamos la maquina virtual que queremos clonar y le hacemos clic derecho, pulsamos en el boton clonar 
![Paso116](images/ubuntu/48.png)

Se nos abrira la siguiente ventana, solo hay un disco duro por lo que usamos ese 
![Paso117](images/ubuntu/49.png)

Iniciara la clonacion y al final veremos como se ha clonado 
![Paso118](images/ubuntu/50.png)
![Paso119](images/ubuntu/51.png)

























