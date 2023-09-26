- [[#Definiciones]]
- [[#Por qué deberíamos usar redes?|Por qué deberíamos usar redes?]]
- [[#Clasificaciones de red|Clasificaciones de red]]
		- [[#Por topología|Por topología]]
		- [[#Por cobertura geográfica|Por cobertura geográfica]]
		- [[#Tecnología de trasmisión|Tecnología de trasmisión]]
## Definiciones
```ad-note
title: Sistema de comunicación
Un *Sistema de comunicación es*:: una infraestructura compuesta por elementos físicos (hardware) y lógicos (software) que permite el intercambio de información entre sistemas terminales. #Easy 
```

```ad-example

En una conversación telefónica, el sistema de3 comunicación sería el teléfono y la red telefónica y los sistemas terminales las personas que hablan entre si.
```

```ad-important
title: Sistema Terminal
Un *sistema terminal o final*:: en el contecto de las rtedes de computadoras, es un dispositivo que es capaz de recibir y mandar información a través de los sistemas de comunicación. #Easy 
```
```ad-example
Un ordenador de sobremesa, un smart watch o una tostadora inteligente son sistemas terminales, que reciben y mandan información constantemente a través de la red
```

```ad-important
title: Red
Una *Red* es:: un sistema de comunicación con sistemas terminales autónomos (es decir, son capaces de gestionar y procesar la información que mandan y reciven) que facilita el intercambio eficaz y transparente de información. #Easy
```

```ad-seealso
title: Notas de clase
*Eficaz* :: Utiliza todos los recursos a su alcance de la mejro manera posible.
*Transparente* ::  Independencia del medio con el que se realiza la conexion 
```

```ad-important
title: Host
Host:: Sistema terminal donde se *consume la información*, un portatil
```

```ad-important
title: Nodo/Elemento de conmutación
Los dispositivos::que se encargan de *enviar* los paquetes entrantes a su destino en la red y *procesarlos*
```

```ad-important
title: Linea de trasmisión
Linea de trasmisión:: Conexión entre los nodos y los host. Una linea de conexión puede ser entre dos hosts, dos nodos o mezcla.
```

```ad-important
title: Subred
Subred:: Infraestructura por la que se transporta la información. Por ejemplo, un cable ethernet mas un router.
```

## Por qué deberíamos usar redes?
?
1. Permiten *Compartir recursos*.
	```ad-example
	Podemos tener una impresora conectada para toda la planta de oficinas, que gestiones múltiples peticiones en una cola de espera, en vez de depender todos de su propia impresora
	```
2. Facilitan la *Escalabilidad del sistema*
	```ad-example
	Es la capacidad de un servicio para seguir funcionando independientemente del volumen de peticiones que se le hagan. Google funciona igual de bien con mil usuarios que conmiles de millones a la vez.
	```
3. Mejoran la *fiabilidad y robustez*
	```ad-example
	Esto se debe a que, si tenemos un fallo catastrófico en una computadora de nuestro servicio. al tener otras conectadas podemos recuperar la información perdida y seguir las actividades de forma habitual.
	```
4. *Reducción de costes*.
	```ad-example
	No es lo mismo depender de una sola CPU con grandes prestaciones que rtepartir la carga en multiples CPUs de menor coste u que se realicen las acciones en el mismo tiempo. Cuanto más potente es el Hardware, más dinero nos cuesta, así que conectar varios dispositivos sale mas barato para el mismo resultado.
	 ```


## Clasificaciones de red

#### Por topología
?
1. ==Bus==: cuando múltiples sistemas terminales/host/nodos están conectados a una red, por la que pasa toda la información.
2. ==Punto a Punto==: cuando dos sistemas terminales están conectados entre si para realizar sus comunicaciones.
3. ==Completamente Conexa==: cuando todos los nodos/sistemas terminales están conectados entre sé, facilitando cualquier tipo de conexión entre ellos. Esta topología es la más costosa de escalar, puesto que requiere una infraestructura exponencial.

#### Por cobertura geográfica
?
1. **LAN**: redes geográficamente concentradas en un único edificio o zona espacial.
2. **MAN**: (deshuso) permiten la interconexión de múltiples dispositivos y recursos en una zona geográfica extensa.
3. **WAN**: son redes a gran escala que abarcan países e incluso continentes.

#### Tecnología de trasmisión
?
1. **Difusión/canal compartido**: Redes cuya conectividad es por señales, por ejemplo wifi o bluetooth.
2. **Redes punto a punto**: Redes cuya conectividad es por conexión física, por ejemplo fibra óptica.
