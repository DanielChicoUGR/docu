
```ad-important
title:Modelo de Referencia
**Modelo de Referencia**:: Es el conjunto de la definición de las distintas capas junto a sus funcionalidades. Para diseñarlo, las funcionalidades distintas se ubican en capas distintas y minimizamos todo lo posible el flujo de capas.
```


## Modelo OSI
### Capas:
?
 1. [[#Capa física]]
 2. [[#Capa de enlace]]
 3. [[#Capa de red]]
 4. [[#Capa de transporte]]
 5. [[#Capa de sesión]]
 6. [[#Capa de presentación]]
 7. [[#Capa de aplicación]]

#### Capa Física:
Se encarga de **la transmisión de información a un niver mecánico**.
```ad-example
Representando la información en bits segun el tipo de cable
```
#### Capa de enlace
Se encarga de la **delimitación, el control de acceso, el control de errores y el control de flujo**.
```ad-note
Delimitación -> Dividir la información en unidades (tramas)
Control de acceso -> Repartir el orden de acceso a los recursos.
Control de flujo -> Evitar que el host envíe mas información de la que se puede procesar.
```
#### Capa de red
Se encarga del **encaminamiento de paquetes de la capa de red (datagrama) de un host a otro. Controla el estado de saturación de la red**
#### Capa de Transporte
Denominaremos a los datos de esta capa *segmentos*.
Transporta **los mensajes de la capa de aplicación entre los puntos terminales de la aplicación y controla el flujo y los errores de extremo a extremo**.
Permite múltiples conexiones entre varios hosts.
#### Capa de Sesión
Permite **delimitar y sincronizar el intercambio de datos, inclutendo los medios para crear un punto de restauración y un esquema de recuperación** (diálogo entre hosts).
#### Capa de Presentación
Su función es **comprimir y cifrar los datos, así como la descripción de los mismos**
#### Capa de aplicación
Es donde **residen las aplicaciones de red y sus protocolos de nivel de aplicación, pj el correo electrónico**.