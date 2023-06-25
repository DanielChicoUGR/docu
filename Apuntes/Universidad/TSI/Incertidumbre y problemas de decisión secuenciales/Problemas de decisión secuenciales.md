Son aquellos en los que la utilidad para el agente depende de la secuencia de acciones

Podemos entenderlos como una generalización de la búsqueda y la planificación que hace uso de la interacción con el entorno y la incertidumbre.
	- Incertidumbre asociada a los efectos de las acciones.
	- Incertidumbre asociada a un conocimiento parcial del entorno.


## Procesos de Decisión de Markov

Proceso de decisión de Markov(PDM)::Es un problema de decisión secuencial para un entorno completamente observable, con un modelo de transición de Markov y recompensas aditivas.

Componentes de un problema de decisión de Markov:
?
- Estados $(s_0,s_1,\dots)$, acciones $(a_1,a_2,\dots)$, un estado inicial $s_0$.
- Modelo de Transiciones: $P(s'|a,s)$ que indica la probabilidad de pasar de $s$ a $s'$ si se ejecuta la acción $a$. Las Transiciones son [[Transiciones de Markov]].
- Utilidad del agente -> Depende de la secuencia de estados
- Objetivo: Maximizar la recompensa acumulada.

```ad-example
title:Robot de recolección de latas

- En cada paso el robot tiene que decidir si debería:
	- Buscar activamente una lata
	- Esperar que alguien tire una lata
	- volver al puesto base para recargar las baterías
- Buscar es lo mejor pero se agotan las baterías, no se puede quedar sin batería en mitad de una acción
- Las decisiones se basan en función del nivel de batería (alto,bajo)

**Recompensa**-> Número de latas recolectado
```

![[Pasted image 20230611175157.png]]

## Política
Política:: Una solución a un Problema de Markov y consiste en asignar a cada estado alcanzable una acción $$\pi:S\rightarrow A$$

Si el agente tiene una política completa entonces no importa el resultado de una acción, ya que el agente siempre sabe que hacer a continuación.

Calidad de la política::Se mide evaluando la utilidad esperada de los posibles históricos de entorno generados por la política

Política óptima $\pi^*$::Política con la mayor utilidad esperada.

### Utilidad para secuencias de acciones
La utilidad de una secuencia de acciones: $U_h=([s_0,s_1,\dots,s_k])$

**Horizonte Finito**:: Existe un tiempo prefijado N tal que después de él no importa nada (el juego se ha acabado), es decir $$\forall k\ \ U_h([s_0,s_1,\dots,s_N])=U_h([s_0,s_1,\dots,s_{N+k}])$$
	La solución óptima puede cambiar a lo largo del tiempo, por tanto la política óptima es no estacionaria

**Horizonte Infinito**::No existe tiempo límite y, por tanto, la acción óptima sólo depende del estado actual y la política óptima es estacionaria.
	La solución óptima solo depende del estado actual y de la política estacionaria a elegir.

### ¿Cómo calculamos la utilidad de una secuencia de estados?

Para resolver esta pregunta nos centraremos en horizontes infinitos, por tanto en políticas estacionarias.

#### Recompensas Aditivas:
$$U_h=([s_0,s_1,s_2,\dots])=R(s_0)+R(s_1)+R(s_2)\dots$$

#### Recompensas con descuento
$$U_h=([s_0,s_1,s_2,\dots])=R(s_0)+\gamma R(s_1)+\gamma^2R(s_2)\dots$$ Donde $\gamma \in [0,1]$ es el ==Factor de descuento== y representa la preferencia de una gente por las recompensas actuales frente a las futuras
 

### Políticas apropiadas
Si el entorno no tiene un estado terminal o nunca lo alcanzamos y usamos recompensas aditivas podemos tener utilidades de $- \infty$ y $+ \infty$ lo que es un problema.

Si usamos recompensas con descuento la utilidad de una secuencia infinita es finita (suma infinita decreciente tiende a un valor.)
![[Pasted image 20230611185833.png]]

**Política apropiada**::Aquella que garantiza al agente alcanzar un estado terminal
**Políticas no apropiadas**:: No garantizan llegar a un estado terminal

### Política óptima
La ==Utilidad esperada de una política $\pi$== es la suma esperada de las recompensas con descuento obtenidas sobre todas las posibles secuencias de estados que pueden darse cuando se ejecuta $\pi$ ![[Pasted image 20230611190526.png]]
La política óptima $\pi^*$ ciene dada por: ![[Pasted image 20230611191054.png]]

### Utilidad de los estados

Idea para calcular la política óptima::Calcular la utilidad de cada estado y usar dichas utilidades para seleccionar la acción óptima en cada estado

La utilidad de un estado $U(s)$ es la utilidad esperada de las secuencias de estados que le pueden seguir.
Como las secuencias dependen la política usada, definimos $U^\pi(s)$ para una política concreta $\pi$. $$U^\pi(s)=E[\Sigma^{\infty}_{t=0}{\gamma^tR(s_t)} | \pi,s_0=s]$$
	- LA utilidad real de un estado U(s) es justamente $U^\pi(s)$
	- Notese la diferencia entre U(s) y R(s):
		- R(s) -> Recompensa a corto plazo.
		- U(s) -> Recompensa a largo plazo.

