**Examen y análisis de un software existente, reestructurándolo y concibiéndolo de otra forma** a partir de la cual se vuelva a implementar, **mejorando la funcionalidad y los atributos de calidad del sistema**, tales como capacidad de evolución, rendimiento, reusabilidad, eficiencia, portabilidad, etc. 
Se trata de pasar de un mal sistema a un buen sistema
##### Riesgos:
- La funcionalidad anterior no se mantiene
- La calidad es inferior
- Los beneficios no se consiguen en el tiempo esperado
##### Motivos:
1. **Mejorar la mantenibilidad**.
	El mantenimiento de un sistema aumenta con el tiempo hasta hacerse demasiado difícil y costoso. En algún momento habrá que hacer uno nuevo con interfaces mas explicitas y módulos funcionales mas relevantes, actualizando además toda la documentación interna y externa del sistema
2. **[[Migración|Migrar]] a una nueva tecnología**. 
	Los sistemas están en continua adaptación a su entorno siendo cada vez menos satisfactorios. Muchas empresas con software operativo y útil se ven forzadas a migrarlos a plataformas de ejecución mas modernas que incluyen nuevo hardware, sistema operativo y/o lenguaje
3. **Mejorar la calidad**.
	Las partes interesadas en un software perciben una bajada de calidad en los sistemas que no se mantienen de forma rigurosa. Se hace necesaria la reingeniería para conseguir aumentar la fiabilidad del mismo.
4. **Prepararse para una mejora de funcionalidad**.
	La funcionalidad del software debe estar constantemente ampliándose para mantener la satisfacción del usuario con este software a lo largo de su tiempo de vida. A menudo la reingeniería mas que buscar añadir funcionalidad busca mejorar la facilidad de añadir funcionalidad en el futuro, por ejemplo, cambiando el estilo arquitectónico o el paradigma de programación
###### Conceptos:
> [!concept]- Ingenieria inversa
> Se trata del movimiento contrario por el que se pasa de los niveles mas altos de detalle a los niveles mas altos de abstracción
> 
> Consiste en la reelaboración del modelo que representa al sistema actual de una forma mas abstracta y fácil de entender. El punto de partida es el código actual y el resultado es una nueva *descripción arquitectónica* o diseño de alto nivel del producto actual. No se trata de cambiar nada, sino de examinar en profundidad el sistema actual.

> [!concept]- Alteracion
> Decidir los cambios que se harán para producir un nuevo producto software a partir del examen del producto actual (ingeniería inversa). Se trata de elaborar una especificación de requisitos y de una *descripción arquitectónica* nueva a partir del producto anterior.

> [!concept]- Ingenieria directa
> Se trata de pasar del nivel mas alto de abstracción en la representación de un sistema, donde solo se muestran las características mas relevantes de un sistema escondiendo los detalles (principio de abstracción) al nivel mas bajo del mismo, con el máximo detalle de sus distintos aspectos (principio de refinamiento)
> 
> Consiste en el desarrollo del nuevo producto software a partir de una nueva *descripción arquitectónica*

$$
\text{Reingenieria} = \text{ingenieria inversa} + \Delta + \text{ingenieria directa}
$$

![[Pasted image 20240416164659.png]]