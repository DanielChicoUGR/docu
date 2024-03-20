Incertidumbre::Falta de seguridad, certeza o confianza sobre algo (RAE)

Los agentes casi nunca tienen acceso al toda la información del entorno por lo que deben comportarse en ambientes con incertidumbre. Para un agente es imposible construir una descripción completa y exacta de cómo se desarrollan sus acciones.

> [!example] Tamaño Planes
> 
> Plan A_90 -> dejar la casa a falta de 90 min de que salga el vuelo, conducir a una velocidad razonable, aparcar y coger el vuelo.
> 
> Nos llevará al aeropuerto a tiempo? -> Puede ser pero muchas cosas pueden salir mal (problemas en la planificación)
> 
> Plan A_120 -> aumenta la creencia en el éxito del plan pero también aumenta la creencia de que la espera aumentará. 
> 
> 
Una posible solución es dotar al agente de una teoría del mundo simple pero errónea que le permita deducir un plan que ==funcione la mayoría de las veces==. Como? -> analizando la importancia relativa de los distintos objetivos, así como de la creencia en que estos se alcanzarán.

# Manipulando Conocimiento Incierto.
> [!example] Ejemplo Medicina y conocimiento complejo
> 
> R1: $\forall p$  Síntoma(p,Dolor_Muelas) $\rightarrow$ Enfermedad(p,Caries)
> 
> R2: $\forall p$ Síntoma(p,Dolor.Muelas) $\rightarrow$ Enfermedad(p,Caries) $\lor$ Enfermedad(p,Dolencia.Encías) $\lor$  Enfermedad(p,Abceso) $\lor \dots$ 
> 
> R3: $\forall p$  Enfermedad(p,Caries) $\rightarrow$ Sintoma(p,Dolor.Muelas)
> 
> La ciencia médica no tiene una teoría completa para su dominio de acción.
> 

Poner en una lista el conjunto completo de antecedente y consecuentes que se necesitan para asegurar una regla sin excepciones tiene demasiado trabajo y usar tales reglas es bastante difícil. En el ejemplo anterior, la conexión entre dolor de muelas y caries no es exactamente una consecuencia lógica en ninguna dirección.


# Grado De Creencia

El conocimiento del agente puede como mucho proporcionar n grado de creencia en las sentencias relevantes. Una opción para representar el grado de creencia es la ==**teoría de la probabilidad**==.

La probabilidad proporciona una manera de resumir la incertidumbre que se deriva de nuestra **pereza e ignorancia**
	- Podríamos creer que la regla que relaciona la caries y el dolor de muelas es, por ejemplo del 0.8
	- El 20% restante resume todas las otras causas posibles de dolor de muelas

# Incertidumbre Y Decisiones Racionales
La presencia de incertidumbre cambia radicalmente la manera en la que un agente toma decisiones

## Principio De la Máxima Utilidad Esperada

Para realizar una elección, el agente debe de tener preferencias entre las diferentes consecuencias posibles de los diversos planes (volvemos a las heurísticas). Utilizaremos el principio de máxima utilidad esperada para conseguir este propósito.

La idea fundamental es que el agente ==es racional== si y solo si elige la acción que le produce la utilidad esperada más alta, en promedio sobre todas las consecuencias de la acción.
