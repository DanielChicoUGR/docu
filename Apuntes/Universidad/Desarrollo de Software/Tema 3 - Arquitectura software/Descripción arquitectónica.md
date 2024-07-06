**Colección de productos para documentar la arquitectura de un sistema**
## Como hacerla
El arquitecto debe **definir los puntos de vista arquitectónicos** desde una lista predefinida de ellos (**librería de puntos de vista**) **en atención a cada una de las inquietudes** que el sistema debe cubrir.
De forma alternativa puede escoger un patron arquitectónico que de respuesta a cada inquietud concreta.
Una vez elegido cada punto de vista, sera necesario describirlo como se ha especificado anteriormente, incluyendo entre otros el lenguaje y métodos de modelado a usar (UML).

| Punto de vista | Tipo de diagrama UML            |
| -------------- | ------------------------------- |
| Estructural    | Componentes, clases             |
| Conductual     | Interacción, actividad, estados |
| Usuario        | Casos de uso, interacción       |
| Distribucion   | Despliegue, interacción         |
## Como identificar los elementos
1. Trabajar a partir de los **requisitos funcionales**
2. Identificar los **elementos funcionales**
3. **Evaluar el conjunto identificado** con los criterios de diseño
4. **Repetir la secuencia** para refinar la estructura funcional hasta que sea solida, **usando uno o mas métodos de refinamiento** entre los siguientes
	- **Generalización:** Reutilización de activos de software en una serie de productos o sistemas similares
	- **Descomposición:** De los subsistemas grandes
	- **Composición:** Reemplazar los elementos mas pequeños con un solo elemento grande que pueda factorizar la parte común entre los pequeños para reducir la cantidad de interacciones
	- **Replicación:** Aumento del rendimiento a costa de inconsistencia
# Ejemplos de estructuras funcionales
## Sistema de vigilancia de la temperatura
![[Pasted image 20240618135505.png]]El sistema esta formado por un componente externo y **dos componentes internos**:
- **Captura de variable**. Obtiene la temperatura con la interfaz `VariableReporting`. Interactúa con el monitor de temperatura externo que invoca a la interfaz `VariableReporting`, es una RPC en XML que usa el protocolo HTTP, por tanto, se usa de forma asíncrona, de forma parecida a las interfaces de mensajería que permite un máximo de 10 invocaciones simultaneas
- **Iniciador de alarma**. Dispara la alarma con la interfaz `LimitCondition`
## Tienda Web dentro de un entorno software ya existente en la empresa
El sistema interactúa con **cinco entidades externas**: los navegadores web de los tres tipos de usuario mas importantes y dos sistemas externos. 
El sistema en si esta compuesto por **cinco componentes principales**, unidos por distintos tipos de conectores.

Los clientes hacen el pedido a través de la tienda, que interactúa a su vez con el gestor de pedidos, el catalogo de productos y el sistema de información del cliente.
Los administradores del catalogo mantienen el catalogo a través de una interfaz Web.
Los que forman parte del equipo de servicio al cliente mantienen la información del cliente mediante un programa cliente de interfaz dedicada.

Cuando se desea consultar el stock de un producto determinado, el catalogo de productos obtiene la información del inventario, que es un sistema que ya existe

Hay también cierta información en cuanto a la naturaleza de las interacciones entre componentes: pueden acceder al sistema simultáneamente hasta 1000 clientes, 80 personas de servicio al cliente y 15 administradores del catalogo. La interacción entre el catalogo de productos y el inventario tiene lugar mediante un protocolo especifico

**Problemas del diagrama:** Las responsabilidades de los componentes no están claras, tampoco los detalles de las interfaces ni los detalles de la interacción entre los distintos componentes. Esto nos hace entender la necesidad de añadir descripciones de texto y otros diagramas que modelen el sistema de forma complementaria, por ejemplo, las interacciones entre componentes puede mostrarse modelando escenarios del sistema

......................................