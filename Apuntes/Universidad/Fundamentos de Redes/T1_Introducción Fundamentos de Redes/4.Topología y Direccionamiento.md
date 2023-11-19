## Jerarquía de 3 niveles
1. [[#Intranets/Redes domésticas]]
2. [[#Redes de Acceso]]
3. [[#Redes Troncales]]

![[Screenshot_2023-09-25-15-51-37-269_com.yygg.note.app.png]]
### Intranets/Redes domésticas
?
Son las redes que generan los routers de los ISP locales y las que se generan en entornos empresariales y laborales. Suelen estar compuesta de una parte de acceso público y otra privada protegida por contraseña/Token de authentication 

### Redes de acceso
?
Las compondrían los ISP a nivel regional y local, que son los proveedores de internet en las casas.  Tienen un alcance moderado.

### Redes Troncales
?
Grandes Operadores de telecomunicaciones. Se les conoce como ISP de nivel 1 o tier 1. Estas empresas poseen cables submarinos que conectan zonas geográficamente alejadas. Algunas empresas montan sus propias redes para su propio servicio, vease amazon o google, que han alcanzado el status de TIer1.

```ad-seealso
1. Acuerdos de Peering y Transito
3. Operadores de Tier1, Tier2, Tier3
1. Puntos neutros, POP, IXP
```

#### Acuerdo de Transito:
?
ISPs de tier 2 y 3 se conectan a ISPs de tier 1 para acceder a conexiones que les sería imposible alcanzar debido a su tamaño limitado, por este servicio el ISP de tier 1 recibe una compensación económica.

#### Acuerdo de Peering
Permite que dos ISP compartan flujo de conexiones sin coste alguno beneficiando a ambas partes. Suele realizarse entre ISP del mismo tier

#### PoP/IX/Puntos intermedios
?
Es una instalación física o virtual en al que diferentes ISPs *interconectan sus redes y dispositivos* para mejorar la eficiencia del tráfico de datos en internet.


## Niveles de Direccionamiento
![[Screenshot_2023-09-25-15-57-44-123_com.yygg.note.app.png]]

### IP (*Internet Protocol*)
?
Es un protocolo que permite la comunicación entre dispositivos conectados a internet o a una red privada. La dirección IP se compone de cuatro partes separadas por puntos.

```ad-example
title: Dirección IP
192.168.0.1 -> Dir IP completa
```

### Puerto
?
Es un número entero que identifica un servicio o aplicación específica en un dispositivo conectado a internet o a una red privada. Los puertos se utilizan para garantizar la correcta recepción y transmisión de datos entre dos dispositivos conectados por medio del protocolo TCP

### URL (Uniform Resource Locator)
?
Es una dirección que identifica un recurso en la Web o en otra red ->? Mala tradución