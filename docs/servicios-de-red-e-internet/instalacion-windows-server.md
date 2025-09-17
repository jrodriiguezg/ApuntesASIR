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

## Configuracion contraseñas

