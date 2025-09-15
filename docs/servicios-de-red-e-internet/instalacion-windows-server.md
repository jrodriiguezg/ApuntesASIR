# Instalacion Windows Server 2022
Yo voy a usar LibVirt en vez de Vmware ya que en fedora silverblue que es lo que uso no se puede instalar otra cosa 

Esta primera captura muestra la pantalla inicial de Libvirt - que es una interfaz grafica para QEMU/KVM, en la esquina superior izquierda esta el boton para crear una maquina virtual

![InicioDeLibvirt](images/Wserver/1.png)

Ahora nos pregunta desde donde queremos instalar nuestra maquina virtual, seleccionamos medio local 

![PantallaCreacionMaquina](images/Wserver/2.png)


La siguiente imagen nos muestra el selector de medios de instalacion, aqui podemos elegir el sistema operativo a instalar y la ISO, para elejir la ISO, debemos pulsar en explorar y se abrira la ventana siguiente 

![Almacenamiento](images/Wserver/4antesde3.png)

Se nos abre la siguiente ventana y tenemos que seleccionar **Explore localmente**, para buscar la ISO en nuestro sistema 

![SeleccionDeISO](images/Wserver/3.png)

En el siguiente paso se configura la memoria RAM del sistema, en este caso vamos a definir 4GB (4096Mb)
![RAM](images/Wserver/5.png)

Ahora creamos el disco duro, en este caso de 60Gb y pulsamos adelante 
![CreacionDiscoDuro](images/Wserver/6.png)

Aqui finalmente vemos como quedaria nuestra instalacion, con un resumen de todo, pulsamos finalizar 

![InstalacionFinal](images/Wserver/7.png)

Ahora iniciara el instalador de Windows Server

![WindowsIniciando](images/Wserver/8.png)

Esta primera pantalla nos pedira que introduzcamos el idioma del sistema (aunque la ISO es la version Española y solo nos deja Español)

![SeleccionDeIdioma](images/Wserver/9.png)

En el siguiente paso solo debemos pulsar en **Instalar**

![PulsarInstalar](images/Wserver/10.png)

Y comenzara a cargar el instalador 

![Instalador](images/Wserver/11.png)

Esta primera pantalla nos pregunta que tipo de version de Windows Server vamos a usar, tenemos 4 versiones diferentes, dos para servidor y dos para datacenter y luego una version en modo escritorio y otra en modo grafico, nosotros cogemos la segunda opcion modo servidor con interfaz grafica

![SelectorVersion](images/Wserver/12.png)

En la siguiente ventana nos pregunta si queremos aceptar el EULA (es obligatorio)

![AceptarEULA](images/Wserver/13.png)

Ahora nos preguntara el tipo de instalacion que queremos si actualizar una version de windows anterior , o una instalacion avanzada desde cero, seleccionamos esta ultima opcion 

![TipoInstalacion](images/Wserver/14.png)

El disco duro virtual es de 60Gb y queremos tener una de 50Gb y otra de 10Gb aproximadamente, para ello pulsamos en el disco a particionar y despues en **Nuevo**

![Particionado](images/Wserver/15.png)

Ahora definimos el tamaño del disco como queremos un disco de 50 y otro de 10 pues en vez de 61000Mb ponemos 51000Mb y asi haria dos pariticiones diferentes y pulsamos en **Aplicar**

![Particionado2](images/Wserver/16.png)

Ahora seleccionamos la particion de 50Gb para instalar el sistema y pulsamos en **Instalar**

![Particionado3](images/Wserver/17.png)

Nos saltara el siguiente aviso, avisando de que faltan particiones del sistema, al pulsar en **Aceptar** las creara de manera automatica 

![Particionado4](images/Wserver/19antesde17.png)

Iniciara la instalacion de Windows Server, se reiniciara automaticamente y nos saldra esta pantalla, en la que introduciremos la contraseña, despues pulsaremos **Finalizar**

![Contraseña](images/Wserver/20.png)

Al fin Windows Server iniciara

![Iniciando](images/Wserver/21.png)

Nos saltara el aviso de la red de local, pulsamos en **Si**

![Iniciando1](images/Wserver/22.png)

## Activacion de usuario administrador 
Nos vamos al lanzador de programas de Windows y buscamos el simbolo del sistema (CMD), pulsamos click derecho y lo abrimos como administrador

![CMD](images/Wserver/23.png)

Ahora escribimos el siguiente comando ``` net user administrador /active:yes``` y pulsamos enter 

![CMD_comando](images/Wserver/24.png)


