# Incertidumbre

## Table of Content

## Definición previa 

Hasta ahora hemos descrito técnicas de representación del conocimiento y razonamiento para un modelo del mundo:
- Completo -> Se conoce todo el conocimiento y los datos
- Consistente -> El conocimiento no da lugar a conclusiones contradictorias
- Inalterable -> El conocimiento siempre es válido y no cambia

Sin embargo, en la mayoría de los dominios de interés no es posible crear tales modelos debido a la presencia de **incertidumbre**

>[!def] 
>Incertidumbre -> Falta de conocimiento seguro y claro de algo (RAE)

## Fuentes de incertidumbre

### Con respecto a los hechos

#### Ignorancia o Desconocimiento

Se pueden dar varios casos, como que un campo de conocimiento sea incompleto, o que, a pesar de ser completo, a veces conviene tomar decisiones con conocimiento incompleto.

>[!example]
>Suele ser conveniente empezar tratamientos médicos, aún sin una respuesta clara o sin respuesta de las pruebas. Por mera seguridad
>

Otras ocasiones, la falta de conocimiento es inevitable 

>[!example]
>Se recae en resultados de eventos puramente aleatorios o indecidibles.
>>[!example]-
>>- ¿Cual será el resultado del sorteo?
>>- ¿Esta persona esta siendo sincera?

#### Vaguedad e imprecisión

Muchos conceptos que usa el ser humano a la hora de hablar son vagos e imprecisos. Conceptos como persona alta, deuda pequeña... Casi siempre aplicables a temas subjetivos o relativos.

### Con respecto a las reglas

Muchas veces las reglas que usan los expertos en determinadas situaciones son realmente reglas heurísticas. El ser humano razona y utiliza reglas que son:
- Inexactas o incompletas
	- “Si es un ave entonces vuela”, ¿y los pingüinos 
	- “Si está en España habla español”, ¿y algunos turistas?
- Imprecisas
	- Cuando haga mucho calor, suba el aire aconidicionado
- Inconsistentes
	- Al que madruga dios le ayuda 
	- No por mucho madrugar amanece más temprano

Esto puede verse como una desventaja/imprecisión. Pero estas características generan un modelo de razonamiento muy potente. Permite con pocas reglas describir conocimiento complejo, en sentido que si solo utilizáramos conocimiento preciso, haría falta una cantidad inmanejable de reglas.


## Razonando con incertidumbre

>[!important] **Objetivo**
>Razonar con conocimiento incompleto, impreciso e incluso parcialmente inconsistente. 


>[!important] **Implementación**
>Es difícil cumplir estos requerimientos utilizando los modelos de razonamiento clásico (la lógica de primer orden). Deben introducirse modelos para manejar información vaga, incierta, incompleta y contradictoria. Crucial para un sistema que funcione en el mundo real

### Cuestiones a resolver por las aproximaciones a la **incertidumbre**

-  ¿Cómo evaluar si se da una condición imprecisa? 
	- Si tiene fiebre alta beber mas agua 
		- -¿Se puede aplicar con 37,8 grados?
		- ¿Cuanta agua le damos entonces? 
- ¿Cómo combinar hechos imprecisos? 
	-  Se con un grado de certidumbre que X es alto, y otro grado de certidumbre que X está delgado 
		- ¿Con que certidumbre puedo afirmar X es alto y esta delgado? 
- ¿Qué confianza se puede tener en las conclusiones? 
	- Si X estudia bastante aprobará; 
	- Juan estudia mucho 
		- ¿Con que certidumbre puedo afirmar que Juan aprobará?
- ¿Cómo combinar la incertidumbre de un mismo hecho deducidos por distintas deducciones? 
	- Si duele la cabeza y la garganta, será amigdalitis con una certeza 
	- Si hay puntos blancos en las amígdalas, será amigdalitis con otra certeza 
		- ¿Si duele la cabeza y la garganta y hay puntos blancos en las amígdalas, con que certeza podemos afirmar que será amigdalitis?

## Algo de historia

Inicialmente la mayoría de los investigadores en IA usaban razonamiento simbólico y evitaban la utilización de números 
>[!note] 
>- Los sistemas expertos no deben usar números puesto que los expertos humanos no lo hacen 
>– Los expertos no pueden suministrar los números requeridos 

Al desarrollar aplicaciones concretas se dieron cuenta de la necesidad de representar y manejar la incertidumbre. MYCIN (años 70), SE para el tratamiento de infecciones bacterianas fue el primer éxito en este campo 

Los métodos numéricos (midiendo la incertidumbre mediante números) son actualmente la herramienta mas utilizada en IA para manejar la incertidumbre.Debido a los éxitos prácticos

## Principales modelos de representación de la incertidumbre

>[!warning]
>La *lógica de primer nivel/orden (LPO)* **no es adecuada** para modelar la incertidumbre. Por lo que son necesarios nuevos modelos.

>[!note]
>##### Nuevos Modelos:
>- Modelos simbólicos:
>	- Lógicas por defecto
>	- Lógicas basadas en mínimos
>		- La asunción del mundo cerrado
>- Modelos numéricos
>	- Probabilidad
>	- Teoría de Dempster-Shaffer
>	- Lógica difusa

### Lógica de Primer Orden (LPO)

#### Características:
1. Es exacta-> Los hechos solo pueden ser ciertos o falsos
2. Completa -> Se conoce todo acerca el campo de trabajo
3. Consistente -> No contiene contradicciones

Por lo tanto la LPO **no puede expresar**:
- Incertidumbre
- Deducciones lógicas que, aunque incorrectas, probables en el mundo real.
- No se puede trabajar con contradicciones, entonces yo sería el papa y dios.

Como la *LPO* asume que **el conocimiento es completo y consistente**, una vez que un hecho se asume es cierto, permanece así, lo cual es un razonamiento monótono. Por lo tanto, añadir nuevo conocimiento siempre incrementa el tamaño de la Base de Conocimiento. Si se tienen una base de conocimiento $BS$ y $BS'$ tal que $BC \subset BC'$ , si con la primera se deduce una expresión $s$, también con $BS'$ se deducirá $s$.

## Modelos simbólicos: 

### Lógica por defecto:

Propuesta por Reiter para solucionar el problema del conocimiento incompleto. Para ello, se introducen una serie de reglas por defecto =="Las reglas por defecto expresan características comunes a un conjunto de elementos que se asumen ciertas salvo que se indique lo contrario"==.

Se tienen reglas con elementos que han sido deducidos pero no son del todo seguros, si aparece un hecho que contradice alguno, se retracta.

Reglas:
-  Si se dan *Condiciones Positivas* y no se sabe de *Condiciones Negativas* entonces asumir *Consecuente*.
	-  "Si se sabe que X es un ave y no se sabe si X no vuela, asumir que vuela"
- Se deben de poder retractar: Si *Consecuente, Condiciones Positivas* y *Condiciones, Negativas* entonces retractar *Consecuente*. 
	- "Si X vuela y es una ave y X no vuela, entonces retractar que vuela

### Asumción del mundo cerrado:

Sirve para manejar el conocimiento incompleto. "Lo que no se puede probar a partir de mi Base de Conocimiento, es falso". Utilizado en Bases de Datos y en PROLOG, y es lo que se ha estudiado y lo que se ha utilizado en CLIPS hasta ahora.

### Inconvenientes:

- Teorías complejas y a veces inconsistentes.
- Si se realiza una serie de deducciones las cuales parten de una deducción la cual en un momento se creía era cierta, puede llegar un punto que se encuentre una inconsistencia con esa deducción inicial y deba retractarse, lo que hace que el resto de lo inferido deba también retractarse, lo cual aumenta mucho la complejidad del sistema. 
- O puede suceder que los hechos deducidos a partir de hechos asumidos por defecto no se retractan si posteriormente los hechos asumidos son retractados.
## Modelos numéricos de la incertidumbre

### Factores de certeza

Los factores de Certeza se calculan a partir de los Grados de Creencia y no Creencia de la hipótesis. Varían entre 0 (creencia nula) y 1 (creencia total)

La relación de los FC y GC es $$FC(H|E)=GC(H|E)-GC(\neg H|E)$$Se quiere saber el grado de certeza que se tiene para hipótesis H con el conjunto de evidencias E.

A diferencia de los Grados de creencia probabilísticos, estos factores de certeza cumplen: $$GC(H|E)+GC(\neg H|E) \neq 1$$
![[T5_Incertidumbre-20240709185021839.webp]]


![[T5_Incertidumbre-20240709185033996.webp]]


![[T5_Incertidumbre-20240709185047123.webp]]