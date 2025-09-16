# Tema 1 Seguridad informatica 

## 1. Necesidad de la seguridad informatica
### 1.1 Seguridad de la informacion y seguridad informatica 
La informacion es el activo mas importante de cualquier empresa, por ello es importante protegerlo. 


**Seguridad de la informacion:** Conjunto de medidas preventivas y reactivas tanto humanas como tecnicas que afectan al almacenamiento y tratamiento de los datos, para reducir en gran medida las posibles amenazas a los mismos. Un aspecto importante a tener en cuanto es la seguridad legal, ya que todas las medidas todas las medidas y procedimientos que establezca la organización para preservar sus
datos deben estar reflejados en su política de seguridad y estar siempre dentro de la ley aplicable.

### 1.2 Sistemas de informacion 
Un sistema de informacion, es un conjunto de elementos organizados que trabajan juntos para administrar, recuperar y procesar datos de forma sencilla 
Algunos de estos elementos son: 
- **Recursos humanos**
- **Datos**
- **Actividades, procedimientos, pasos y tareas a seguir**
- **Recursos informaticos**

### 1.3 Sistema de gestion de la seguridad de la informacion (SGSI)

**SGSI:** Conjunto de politicas, procedimientos y recursos que una organizacion utiliza para proteger sus activos.
La base para desarollar un SGSI es identificar que activos se deben proteger y en que grado, para ello se utilizan las normas **ISO 27001** e **ISO 27002** asi como el **Ciclo de Deming** para asegurar la mejora continua 

**El ciclo de Deming se aplica en cuatro niveles:**
- **Planificar:** Se definen las politicas de seguridad, el alcance del SGSI y se realiza un analisis de riesgos 
- **Hacer:** Se implemente el SGSI, se ejecuta el plan de gestion de riesgos
- **Verificar:** Se monitorean las actividades y se realizan auditorias externas 
- **Actuar:** Se implementan mejoras, acciones preventivas y correctivas

Aspectos importantes para la implantacion del estandart **ISO 27001**: 
1. Compromiso y concienciacion 
2. Organizacion 
3. Analisis de procesos y servicios 
4. Gestion de riesgos 
5. Mejora continua 

## 2. Bases de la seguridad 
La seguridad informatica, un concepto que Spafford considera inalcanzable. Por eso se prefiere hablar de fiabilidad que es la probabilidad de que un sistema se conporte como se espera. 

### 2.1 Conceptos de seguridad informática: fiabilidad, confidencialidad, integridad y disponibilidad 
Un sistema informatico se considera fiable cuando cumple con tres propiedades, conocidas como la triada **CID**: 
- **Confidencialidad:** Asegura que solo los usuarios autorizados tengan acceso a la informacion y recursos del sistema 
- **Integridad:** Garantiza que solo los elementos autorizados puedan modificar, borrar o crear recursos del sistema 
- **Disponibilidad:** Mantiene los recursos accesibles para los usuarios autorizados en todo momento 

![Triada_CID](images/cid.png)

### 2.2 Alta disponibilidad
 Es la capacidad de un sistema para estar operativo sin interrupcion, 24 horas del dia, 7 dias de la semana 365 dias del años. Para medirla se usan dos metricas: 
 - **Tiempo medio entre fallos (MTTF)**
 - **Tiempo medio de recuperacion (MTTR)**

### 2.3 Medidas y mecanismos de seguridad
Para mantener la seguridad del sistema informatico se necesitan establecer unas medidas y mecanismos de seguridad, las medidas son genericas y se agrupan segun el objetivo: 
1. En base al elemento o activo que se protege 
    - **Seguridad fisica:** Trata de proteger el hardware, teniendo en cuenta la ubicacion y las amenazas de tipo fisico; robos, catastrofes naturales, etc. 
    - **Seguridad logica:** Protege el software tanto a nivel de sistema oerativo como de aplicaciones, sin perder nunca de vista el elemento fundamental a proteger la informacion o dato del usuarios 
2. En base al momento en el que se protege
    - **Seguridad activa:** Son preventivas y evitan grandes daños en los sistemas informaticos, por tanto se consideran acciones preventivas a un ataque 
    - **Seguridad pasiva:** Son correctivas, minimizan el impacto y efectos causados por accidentes es decir se consideran medidas o acciones posteriores a un ataque o incidente.

En cuanto a los mecanismos de seguridad, se dividen en tres grupos: 
1. **Prevencion:** 
    - Evitan desviaciones respecto a las politicas de seguridad 
2. **Deteccion:**
    - Detectan las desviaciones, violaciones o intentos de violacion del sistema de seguridad 
3. **Recuperacion:**
    - Se aplicacion cuando se ha detectado una violacion de la seguridad del sistema para recuperar su funcionamiento normal 

### 2.3 Elementos vulnerables y vulnerabilidades 
Los elementos mas vulnerables de un sistema operativo, son: 
- **Hardware:** Son elementos tangibles o fisicos de nuestro sistema. 
- **Software:** Son los elementos logicos del sistema. 
- **Datos:** Estan constituidos por aquella informacion logca que procesan los programasas utilizando el hardware 
- **Otros:** Son elementos fingibles es decir los que se usan y gastan, como DVD, cintas de copias de seguridad. 

Las vulnerabilidades de los sistemas se pueden clasificar segun: 
- **Vulnerabilidades de origen fisico:** Se relacionan con el acceso fisico a las instalaciones. Si no se mantiene una buena politica de acceso al sistema 
- **Vulnerabilidades de origen natural:** Son imprevisibles e inevitables causadas por desastres naturales, aunque se pueden minimizar sus daños 
- **Vulnerabilidades de hardware:** Relacionadas con el mal funcionamiento de los dispositivos fisicos, por diversas causas: mal diseño de un componente, desgaste fisico, errores de fabricacion, etc. 
- **Vulnerabilidades de software:** Son las mas evidentes y conocidas, se basan en errores de programacion o diseño tanto de sistemas operativos o programas 
- **Vulnerabilidades de red:** Pueden conllevar la filtracion de informacion, o el acceso no autorizado a un sistema informatico, un elemento muy condicionante en la aparición de vulnerabilidades es la elección de la topología de la red (según cuál se elija seremos más sensibles a unas u otras amenazas).
- **Vulnerabilidades de factor humano:** Es el eslabon mas debil e incontrolable, ya que mediante ingenieria social se puede explotar y usar para acceder a los datos. 

### 2.4 Legislacion sobre seguridad
Algunas de las normas y estandares sobre la seguridad de la informacion, son: 
- **ISO 27000:**  Esta norma sirve como un glosario. Proporciona los términos y definiciones fundamentales que se utilizan en toda la serie 27000
- **ISO 27001:** Este es el estándar principal para certificar un Sistema de Gestión de Seguridad de la Información (SGSI). Contiene los requisitos que una organización debe cumplir para establecer, implementar, mantener y mejorar su seguridad de la información
- **ISO 27002:** A diferencia de la 27001, esta norma es una guía de buenas prácticas. Detalla un amplio catálogo de 133 controles de seguridad (organizados en 11 dominios) y 39 objetivos
- **ISO 27005:** Esta norma se centra específicamente en la gestión de riesgos. Proporciona directrices sobre cómo identificar, analizar, evaluar, tratar y monitorizar los riesgos relacionados con la seguridad de la información

## 3. Amenazas 




