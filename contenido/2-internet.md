# Internet

## ¿Qué es?

[Internet (según Wikipedia):](https://es.wikipedia.org/wiki/Internet)
```
Internet es un conjunto descentralizado de redes de comunicación interconectadas que utilizan la familia de protocolos TCP/IP, lo cual garantiza que las redes físicas heterogéneas que la componen formen una red lógica única de alcance mundial. 

Sus orígenes se remontan a 1969, cuando se estableció la primera conexión de computadoras, conocida como ARPANET, entre tres universidades en California (Estados Unidos).
```

Si bien esta definición está muy bien, por ahí, no nos ayuda a terminar de entender bien el concepto. Para lograr nuestro objetivo vamos a dividirla en pequeñas partes y analizarlas mejor.

```
Internet es un conjunto descentralizado de redes de comunicación interconectadas.
```

Para poder comunicar 2 computadoras podemos hacerlo utilizando el concepto de red. Esto significa que de alguna forma voy a conectar estas máquinas y poder hacer cosas como copiar archivos entre sí. Existen distintas formas de conexión como pueden ser [fibra óptica](https://es.wikipedia.org/wiki/Fibra_%C3%B3ptica), [wifi](https://es.wikipedia.org/wiki/Wifi) o utilizar un [cable de red (UTP)](https://es.wikipedia.org/wiki/Par_trenzado_no_blindado).

Nuestra red puede crecer a medida que vamos conectando nuevos dispositivos, por ejemplo iniicialmente sólo tengo una máquina conectada por wifi pero con el correr del tiempo me compro un celular y una tablet que tambien puedo conectar a mi red hogareña. Vemos en este último caso como hoy en día existen más dispositivos que se pueden terminar uniendo a una red.

De esta parte de la definición podemos rescatar que parece que internet no es tanto una 'nube' como se suele decir, 

![Internet como Nube](../assets/internet/nube.png)

sino que tiene más que ver con un montón de computadoras que se comunican entre si.

![Internet como Nube](../assets/internet/internet_compus_conectadas.png)

```
que utilizan la familia de protocolos TCP/IP.
```

Ya mencionamos que las computadoras se van a comunicar entre si y la definición menciona algo de [TCP/IP](https://es.wikipedia.org/wiki/Modelo_TCP/IP). Por ahora podemos definir que este nuevo concepto es algo interno que tiene que ver con la forma en la que se comunican las computadoras. Más adelate vamos a explicar cada uno de estos conceptos dividiendolos en TCP e IP.

```
 lo cual garantiza que las redes físicas heterogéneas que la componen formen una red lógica única de alcance mundial.
```

Más allá del chiste, esta parte de la definición nos cuenta una de las característica más importante que tiene Internet y es el echo de poder conectarnos/comunicarnos desde cualquier parte del mundo. Este concepto es difícil de visualizar porque significa que son millones de dispositivos conectados entre si estando a mucha distancia unos de los otros ([¿dónde estan los cables?](http://www.infobae.com/2014/10/13/1601116-el-cable-que-las-toninas-conecta-internet-toda-la-argentina/)). Internet nos abstrae completamente de eso y podemos utilizarla sin problemas.

![Internet Cables](../assets/internet/internet_cables.png)

```
Sus orígenes se remontan a 1969, cuando se estableció la primera conexión de computadoras, conocida como ARPANET, entre tres universidades en California (Estados Unidos).
```

El final de la definición nos habla sobre el orígen de Internet. Si bien puede no gustarnos mucho la historia en general nos viene bien saber de donde vienen las cosas para entender porque las cosas son como son y el caso de Internet no es la excepción.

## Historia

En 1970 [Vint Cerf](https://es.wikipedia.org/wiki/Vinton_Cerf) y [Bob Kahn](https://es.wikipedia.org/wiki/Robert_Kahn) crean un proyecto militar llamado [ARPANET (Advance Research Projects Agency NETwork)](https://es.wikipedia.org/wiki/ARPANET).

La idea era crear un sistema de comunicación que pueda sobrevivir un ataque nuclear y para lograr este objetivo tenía que ser distribuido (No estar centralizado), tener conectividad desde principio a fin y también se valoraba poder escalar o crecer.

En esa época no existía un método standard para comunicarse por red, es por esto que Vint Cerf y Bob Kahn inventan un protocolo llamado Internet Working Protocol y de esta forma nace Internet, red de redes como una una filosofía de diseño.

![Vint Cerf & Bob Kahn](../assets/internet/Vint-Cerf-And-Bob-Kahn.jpg)
_Vint Cerf & Bob Kahn_

Características de Internet:

* Posibilidad de compartir conocimiento con alcance mundial
* Acceso casi inmediato sin importar la distancia física entre equipos
* Herramienta muy valiosa para desarrollo colaborativo

Ahora que entendemos la definición de Internet, su utilidad y conocemos un poco su historia nos vamos a poner un poco más técnicos.

## Conceptos de comunicaciones y redes

### Unidades de datos

Las computadoras son equipos digitales, es decir que su información se maneja y se guarda codificada en un formato [binario](https://es.wikipedia.org/wiki/Sistema_binario), ya que esa información son en realidad señales electrónicas, que manejan dos estados posibles, que pensaremos numéricamente como 0 y 1 (en la realidad física, son señales eléctricas de voltaje bajo o alto, podríamos pensarlas como _apagado_ y _encendido_).

Los datos se agrupan en distintas unidades de medida:

- Un [BIT](https://es.wikipedia.org/wiki/Bit) es la unidad mínima de información empleada en informática, en cualquier dispositivo digital, o en la teoría de la información. Es ese 0 o 1 que recién mencionamos.

- Un [BYTE](https://es.wikipedia.org/wiki/Byte), abreviado _b_, son 8 bits.

- Un [KILOBYTE](https://es.wikipedia.org/wiki/Kilobyte), abreviado _Kb_, son 1024 b.

- Un [MEGABYTE](https://es.wikipedia.org/wiki/Megabyte), abreviado _Mb_, son 1024 Kb.

- Un [GIGABYTE](https://es.wikipedia.org/wiki/Gigabyte), abreviado _Gb_, son 1024 Mb.

- Un [TERABYTE](https://es.wikipedia.org/wiki/Terabyte), abreviado _Tb_, son 1024 Gb.

- Hay unidades mayores, que al menos por ahora raramente referimos (petabyte, exabyte, zettabyte, yottabyte, siempre aumentando de a 1024 veces).

>Ojo, no confundir un MEGABYTE con un [MEGABIT](https://es.wikipedia.org/wiki/Megabit), abreviado _Mbit_, o un KILOBYTE con un [KILOBIT](https://es.wikipedia.org/wiki/Kilobit), abreviado _Kbit_. Un kilobit son 1000 bits, y un megabit son 1000 kilobits. Son medidas habitualmente utilizadas para medir velocidad de transmisión de datos por segundo (Mbit/s o Kbit/s, lo que llamamos _tasa de bits_), por ejemplo en placas de red o módems.

Estas unidades nos sirven para expresar cantidades de información, pero ¿cómo se envía de una computadora a otra?

### Soportes de comunicación:

Como ya mencionamos existen distintas formas (distintos soportes físicos) de conectar computadoras y cada una tiene sus pros y contras:

* Electricidad, a través de cables.
* Luz, a través de fibra óptica, un método más caro pero con altísima velocidad de transmisión y sin pérdida de datos (el cable eléctrico puede recorrer una distancia relativamente corta, porque tiene pérdidas).
* De forma inalámbrica, lo que conocemos como Wifi, que son ondas electromagnéticas (por su frecuencia son lo que llamamos microondas). Tienen un alcance limitado (varía según la frecuencia) y mucha pérdida por distancia u obstáculos.

### Protocolos:

Los equipos, que pueden no solo ser computadoras, sino también routers, switches, módems, teléfonos o aparatos cualesquiera conectados a una red (algo en crecimiento permanente en el marco de lo que llamamos IoT, _"Internet of Things"_, Internet de las Cosas), no solo necesitan un soporte físico para comunicarse, sino un idioma común, un "contrato" sobre cómo vincularse. Eso es lo que llamamos **protocolos**.

#### Internet Protocol (IP)

IP (Protocolo de Internet) es el protocolo que utiliza Internet. Es algo así como el domicilio, único e irrepetible, de un equipo conectado a Internet. En la actualidad encontramos dos versiones, [IPv4](https://es.wikipedia.org/wiki/IPv4) e [IPv6](https://es.wikipedia.org/wiki/IPv6). Una _dirección_ de IP escrita en IPv4 son 4 cifras de valores de 0 a 255, separadas por puntos (puede ser, por ejemplo, `176.45.117.8`). Esa combinación da más de 4.200.000.000 (cuatro mil doscientos millones) de direcciones posibles, pero al ritmo de crecimiento de la red y de la cantidad de equipos, ya está resultando insuficiente. Por eso se está migrando a un nuevo formato, el IPv6, que comprende 8 grupos de 4 dígitos hexadecimales separados por el signo dos puntos (por ejemplo, `2001:0DC8:75A4:0000:0000:8A2E:0370:7334`), cuya combinación da el inimaginable total de 340 sextillones. Podremos habitar Neptuno antes de que se terminen las direcciones de IPv6.

#### Ejemplos de dirección de IP en sus dos versiones utilizadas actualmente: 

[IPv4](https://es.wikipedia.org/wiki/IPv4)
```
  174.129.14.120
```
* Cada una de estas secciones van desde 0 a 255 representan un Byte
* Tiene una longitud de 32 bits
* Se pueden generar 4 Billones de direcciónes únicas

![IPv4 Binario](../assets/internet/Ipv4_address_Spanish.svg.png)

[IPv6](https://es.wikipedia.org/wiki/IPv6)
```
3FFE:F200:0234:AB00:0123:4567:8901:ABCD
```
* Tiene una longitud de 128 bits
* Se pueden generar muchas pero muchas direcciones únicas

![IPv6 Binario](../assets/internet/Ipv6_address-es-corrected.svg.png)

### DNS: Domain Name System

Los seres humanos somos buenos para recordar nombres pero no tanto con números. Es por esto que existe un concepto denominado [Sistema de nombres de dominio o Domain Name System (DNS)](https://es.wikipedia.org/wiki/Sistema_de_nombres_de_dominio) que permite que nosotros recordemos la dirección de google.com y las computadoras van a traducir ese nombre en la dirección/es IP que corresponda/n.

**Ejemplo:**
```
Dominio: www.google.com
IP: 174.129.14.201
```

* Forma de conectar nuestra compu al destino
* Estan divididos en grupos: .com .org .net
* Se distribuyen en forma jerárquica
* Fué creado para que sea un protocolo de comunicación Público/Abierto

**Ejemplos reales**

Podemos utilizar el comando [nslookup](https://norfipc.com/redes/como-usar-comando-nslookup-windows.html) (Más información en [Wikipedia](https://es.wikipedia.org/wiki/Nslookup)) desde la consola del sistema operativo (en Windows: Menú inicio -> Símbolo de Sistema) para obtener información sobre los DNS.

```
$ nslookup google.com

Non-authoritative answer:
Name:      google.com
Addresses: 2800:3f0:4002:802::200e
           172.217.172.78
```

```
$ nslookup developer.mozilla.org

Non-authoritative answer:
Name:      d1avawhiqh9uo1.cloudfront.net
Addresses: 2600:9000:21f4:2a00:13:e62f:2040:93a1
           2600:9000:21f4:0:13:e62f:2040:93a1
           2600:9000:21f4:2e00:13:e62f:2040:93a1
           2600:9000:21f4:3a00:13:e62f:2040:93a1
           2600:9000:21f4:9e00:13:e62f:2040:93a1
           2600:9000:21f4:4400:13:e62f:2040:93a1
           2600:9000:21f4:8600:13:e62f:2040:93a1
           2600:9000:21f4:1200:13:e62f:2040:93a1
           13.227.70.71
           13.227.70.81
           13.227.70.106
           13.227.70.31
Aliases:   developer.mozilla.org
```

* Tanto DNS como IP están diseñados para poder escalar.
* No existe una conección directa para que los datos lleguen de una computadora a otra.
* No necesita seguir  un camino fijo ya que puede tomar distintos caminos
* Los datos viajan en paquetes.
* En los paquetes viajan distintos tipos de datos.
* Se puede dividir en paquetes más chicos si el contenido es muy grande.
* Al llegar todos los paquetes se puede restablecer el contenido original de gran tamaño.
* Cada paquete sabe de donde viene y hacia donde va.

En Argentina podemos comprar u obtener información sobre un dominio utilizando [NIC.ar](https://nic.ar) (que ahora se administra desde la web de AFIP) para los dominios de Argentina, los .ar (.com.ar, .gob.ar, .org.ar, etc). También podemos utilizar servicios como [GoDaddy](https://ar.godaddy.com) para obtener dominios del tipo .com o similar.

### Routers:

En la sección anterior mencionamos que las computadoras se van a enviar datos en formato binario y pueden estar divididos en paquetes según su tamaño. Para poder redireccionar estos paquetes y que lleguen a destino necesitamos [routers](https://es.wikipedia.org/wiki/Router).

* Se encargan de direccionar los paquetes.
* Si una ruta esta congestionada busca otro camino.
* El router busca el camino más barato para llegar a destino.
* El camino puede no ser el más efectivo.
* Fault Tolerant: Se pueden mandar paquetes por distintos caminos si hay algún problema en algún lado.

### TCP: Transmission Control Protocol

El [Protocolo de Control de Transmisión o Transmission Control Protocol (TCP)](https://es.wikipedia.org/wiki/Transmission_Control_Protocol) garantiza que los datos serán entregados en su destino sin errores y en el mismo orden en que se transmitieron. 

* Maneja o administra que todos los paquetes enviados y recibidos.
* Es como un correo garantizado.
* Al recibir todos los paquetes TCP firma que esta todo bien y le envía a la otra computadora un recibo.
* En caso de faltar algún paquete TCP no lo va a confirmar y el server va a tener que enviar todos los paquetes restantes.

### TCP/IP:
Podemos decir entonces que:

**TCP:**  Garantiza que los datos serán entregados en su destino sin errores y en el mismo orden en que se transmitieron.

**IP:**   Identifica, de manera lógica y jerárquica, a una Interfaz en red (elemento de comunicación/conexión) de un dispositivo.

Podemos tener una vista con un poco de abstracción:

```
DNS
TCP/IP & Routers
Cables / Radio / Wifi
```

Ahora que vimos todos estos conceptos podemos ver que Internet se parece más a algo como esto:

![TCP/IP](../assets/internet/ipdirectindirect.png)

```
Gracias a todos estos conceptos podemos comunicar computadoras enviando y recibiendo datos en formato binario que viajan en pequeños paquetes. Con todos estos conceptos podemos entender qué es internet y cómo funciona a un más bajo nivel sin entrar mucho en detalle. Al ser programadores esta bueno conocer un poco sobre las cosas que vamos a estar utilizando en nuestros programas.
```


## Videos

[Code.org®](https://code.org) es una organización sin fines de lucro dedicada a expandir el acceso a la informática y aumentar la participación de las mujeres y minorías. Crearon los siguientes videos para explicar estos conceptos y mucho más. Son muy buenos y recomiendo que los miren. Tienen subtítulos en español si activan los mismos 

![Videos](../assets/internet/videos.png)

### Internet
* [¿Qué es Internet?](https://www.youtube.com/watch?v=Dxcc6ycZ73M)
* [Internet: Alambres, Cables y Wifi](https://www.youtube.com/watch?v=ZhEf7e4kopM)
* [Internet: Direcciónes IP y DNS](https://www.youtube.com/watch?v=5o8CwafCxnU)
* [Internet: Paquetes, Routing y Confiabilidad](https://www.youtube.com/watch?v=AYdF7b3nMto)
* [Internet: HTTP y HTML](https://www.youtube.com/watch?v=kBXQZMmiA4s)

### Extras
* [Internet: Encriptado y Llaves públicas](https://www.youtube.com/watch?v=ZghMPWGXexs)
* [Internet: Seguridad Informática y Crimen](https://www.youtube.com/watch?v=AuYNXgO_f3Y)
* [Internet: ¿Cómo funciona un buscador?](https://www.youtube.com/watch?v=LVV_93mBfSU)

