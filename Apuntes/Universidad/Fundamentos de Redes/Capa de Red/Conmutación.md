## Qué es??
***Conmutación***:: Acción de cursar tráfico para establecer o determinar un camino que permita trasmitir información extremo a extremo.

Diferentes tecnologías de conmutación:
- [[#Conmutación de circuitos]]
- [[#Conmutación de paquetes]]: Datagramas o circuitos virtuales

#### Conmutación de Circuito
![[Screenshot_2023-09-25-16-50-44-275_com.yygg.note.app.png]]
-------------------------------------------------
![[Screenshot_2023-09-25-16-54-33-162_com.yygg.note.app.png]]
##### Ventajas:
?
- La transmisión se realiza en tiempo real, adecuado para la voz
- Uso permanente de recursos, el circuito se mantiene toda la sesión
- No hay contención, no se compite por acceder al medio de intercambio
- El circuito es fijo, no hay decisiones de encaminamiento una vez establecido
- Simplicidad en la gestión de los nodos médios

##### Inconvenientes:
?
- Retraso en el inicio de la comunicación
- En ocasiones uso no eficiente de recursos
- El circuito es fijo. No se reajusta la ruta de comunicación

```ad-done
title: Ventajas
```

```ad-error
title: Desventajas
```

#### Conmutación de Paquetes (Datagramas)
![[Screenshot_2023-09-25-17-02-51-227_com.yygg.note.app.png]]
###### En que consiste?
?
- Transmisión en unidades de datos (paquetes) independientes
- No es orientado a conexión
- En cada salto se realiza -> Store & forward (Almacenamientos y paso del paquete)
- Cada paquete debe contener en su cabecera la dirección origen y destino
- Los paquetes pueden seguir rutas diferentes y llegar desordenados