# Que Se Necesita:
1. Convertir los puntos de la ruta (origen, destino y puntos vía) en coordenadas de articulaciones ([[Modelo cinemático inverso]]). Para la ruta con m puntos en un manipulador con n articulaciones $\{q_{1_1},q_{2_1},\dots,q_{n_1}\},\{q_{1_2},q_{2_2},\dots,q_{n_2}\},\dots,\{q_{1_m},q_{2_m},\dots,q_{n_m}\}$ 
2. Para cada articulación, se interpolan untos obtenidos en el paso anterior:
	```
	para i=1 hasta n:
	 $f_{q_i}(t) \leftarrow Interpolar(q_{1_i},q_{2_i},\dots,q_{n_i})$
	 ```
	 ***Resultando en una función para cada articulación*** 
3. Para cada articulación, se muestrea su función $f_{q_i}(t)$ dando lugar a los valores intermedios que tomará la variable de esa articulación durante la trayectoria

De esta forma se consigue la posición y orientación deseadas en los puntos vía. En el trayecto entre los puntos vía, la formación de la ruta es bastante simple en el espacio de articulación, pero compleja si la describimos en espacio cartesiano.