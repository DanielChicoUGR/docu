- [[#Definiciones|Definiciones]]
	- [[#Comunicación Real|Comunicación Real]]
	- [[#Comunicación Virtual:|Comunicación Virtual:]]
	- [[#Entidades de nivel N:|Entidades de nivel N:]]
	- [[#Entidades Pares:|Entidades Pares:]]
	- [[#Protocolo:|Protocolo:]]
	- [[#Interfaz:|Interfaz:]]
	- [[#Servicio:|Servicio:]]
	- [[#Pila de protocolos:|Pila de protocolos:]]
	- [[#Arquitectura de red:|Arquitectura de red:]]
- [[#Retardos en la comunicación:|Retardos en la comunicación:]]
	- [[#Retardo en el procesamiento *nodal*|Retardo en el procesamiento *nodal*]]
	- [[#Retardo de cola|Retardo de cola]]
	- [[#Retardo de transmisión|Retardo de transmisión]]
	- [[#Retardo de propagación:|Retardo de propagación:]]
	- [[#Retardo total:|Retardo total:]]
- [[#Tipos de Servicios:|Tipos de Servicios:]]
	- [[#Tipos de Servicios:#Según conexión|Según conexión]]
	- [[#Tipos de Servicios:#Según confirmación:|Según confirmación:]]


## Definiciones
#### Comunicación Real
?
Es el *camino verdadero* por el que pasa la información cuando se transmite por la red.

```ad-example
Dos políticos de diferente pais con dos traductores cada uno, el camino real de la información sería:
Político1 -> Traductor1 -> Traductor2 -> Político2 
```

#### Comunicación Virtual:
?
Describe el intercambio de información, ocurre entre capas del mismo tipo.

```ad-example
 En el ejemplo anterior, los políticos no están hablando con los traductores, hablan entre sí a través de los traductores. La comunicación virtual seía entre los dos políticos, los dos traductores ...
```

#### Entidades de nivel N:
?
Los elementos hardware o software que existen en la capa N, siendo N=1 la capa física y N=7 la capa de aplicación del modelo [[Diseño y estandarización de Redes#Modelo OSI|OSI]] 

#### Entidades Pares:
?
Las entidades a nivel N del emisor y el receptor (Sistemas terminales o nodos) en un intercambio de información.

#### Protocolo:
?
Reglas que regulan el intercambio de información *[[#Comunicación Virtual|virtual]]* entre capas iguales

#### Interfaz:
?
Reglas que regulan el intercambio de información [[#Comunicación Real|real]] entre capas distintas

#### Servicio:
?
Funcionalidad o presentación de una capa específica. Una capa que usa el servicio de otra se le llama *usuario del servicio* y a la que lo provee se le llama *proveedora del servicio*

#### Pila de protocolos:
?
Especificación de los protocolos de cada capa.

#### Arquitectura de red:
?
Es la combinación de la pila de protocolos y el modelo de referencia.

```ad-example
El modelo OSI le falta la pila para ser una arquitectura, asiq eu solo es un modelo.
Sin embargo *TCP/IP* si que posee una pila de protocolos por lo que se le considera una arquitectura
```


## Retardos en la comunicación:
![[Pasted image 20230929105558.png| ]] 
![[Pasted image 20230929105705.png]]

#### Retardo en el procesamiento *nodal*
?
Es el tiempo requerido para *examinar la cabecera* del paquete y determinar *dónde* hay que *enviarlo*. Puede revisar errores a nivel de *BIt*

#### Retardo de cola
?
Ocurre mientras el paquete *espera* para ser transmitido a través del enlace. *Dependerá* del número de *paquetes* que *hayan llegado antes* a la cola.

#### Retardo de transmisión
El tiempo necesario para introducir todos los bits del paquete en el enlace.

```ad-important
title: Retardo de transmisión
$$T_{t}=\frac{L}{V_t}$$
- $T_{t}$ -> Tiempo (segundos)
- $L$ -> Tamaño del paquete(en bits)
- $V_{t}$ -> Velocidad de la red (en bits/seg)
```
```ad-example
Un paquete pesa 1MB y la velocidad de trasmisión de la red es 2kB por segundo, Tardará 1MB/2kB= 500 segundos $\approx$ 8 minutos
```

#### Retardo de propagación:
El tiempo necesario para moverse desde el principio del enlace hasta el router destino. Depende del cable/medio de transmisión que utilices y su velocidad. La velocidad máxima de trasmisión la marca la relatividad general en la velocidad de la luz.

```ad-important
title: Retardo de Propagación
$$T_{t}=\frac{D}{V_p}$$
- $T_{t}$ -> Tiempo (segundos)
- $D$ -> Distancia entre los nodos (en metros)
- $V_{t}$ -> Velocidad del medio (en metros/seg)
```

#### Retardo total:
?

```ad-important
title: Retardo Total
$$T_{total}=T_{proc}+T_{cola}+T_{transm}+T_{propag}$$
Se define com,o la suma de todos los retardos vistos:
- $T_{proc}$ -> [[#Retardo en el procesamiento *nodal*|Retardo de procesamiento]]
- $T_{cola}$ -> [[#Retardo de cola|Retardo de cola]]
- $T_{transm}$ -> [[#Retardo de transmisión|Retardo de transmision]]
- $T_{propag}$ -> [[#Retardo de propagación|Retardo de propagación]]
```


## Tipos de Servicios:

### Según conexión
?
- *Orientados a Conexión (SOC)* -> Depende de una respuesta para poder realizar la comunicación (acuse de recivo)
	- ![[Pasted image 20230929112855.png]]
- *No Orientado a Conexión (NSOC)* -> Puede realizarse sin saber si la otra persona está disponible. (Un servicio de cartas (postal))

### Según confirmación:
?
- *Servicio confirmado (ACK)* -> Viene de las iniciales de ACKnnowledge, manda un acuse de recibo al emisario
	- ![[Pasted image 20230929112911.png]]
- *Servicio no confirmado* -> No envía nada cuando recibe la información


