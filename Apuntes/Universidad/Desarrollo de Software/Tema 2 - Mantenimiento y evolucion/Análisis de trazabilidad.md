Ante una SC en el mantenimiento, el análisis de trazabilidad es un **proceso iterativo que identifica y actualiza en cada paso el impacto que el cambio tendrá en el sistema**, desde la especificación del requisito hasta su implementación final, **reevaluando el diseño del sistema** (requisitos, diagramas de clases, métodos, implementación y documentación) que podría verse afectado conocido como *Impact Set (IS)*.

Un primer boceto de este análisis consiste en describir el *Starter Impact Set (SIS)*. Para ello, a partir de conceptos del sistema relacionados con el SC identificados mediante sustantivos clave en la especificación del nuevo requisito funcional, se creara un grafo con cuatro grandes silos ordenados de izquierda a derecha y según el ciclo de vida del software
- **Requerimientos**
- **Diseño**
- **Código**
- **Pruebas**

La **trazabilidad horizontal** se representara con **líneas discontinuas**.
La **trazabilidad vertical** se representara con **líneas continuas**.
```ad-abstract
title: Tipos de trazabilidad

- **Horizontal**. Como afectan los productos de una fase en la siguiente
- **Vertical**. Como afectan/impactan productos dentro de una misma fase
```
Los productos **afectados directamente** por productos de la fase anterior se representaran en **gris claro**
Los productos **afectados indirectamente** por productos de la misma fase se representaran en **gris oscuro**

Un ejemplo de sustantivos clave puede verse en esta descripción

*Añade al cajero automático un nuevo tipo de **pago** mediante una **tarjeta** de debito expendida por el banco Chautauqua*

Los conceptos podrían ser: "tarjeta", "pago"
Cuando se usa OO, los conceptos serán implementados como clases y, algunos menos importantes como simples atributos.

En arquitecturas no OO o arquitecturas OO que hacen una transformación de los conceptos en clases de manera incorrecta se puede hacer necesario buscar si los conceptos identificados ya aparecían en otros requisitos, clases o el código fuente. Pero si se trata de una arquitectura OO correctamente implementada, podemos movernos de izquierda a derecha en el grafo pasando de los requisitos a las clases y de estas a los métodos y de estos a las pruebas.

![[Pasted image 20240416162052.png]]