
# Dominio:
?
- Conjunto arbitrario $X$
- Conjunto de objetos del que queremos saber el label 
- Normalmente los elementos de este conjunto se representan como un vector de características.
- A los propios puntos del espacio se les denomína **instancias** y a $X$ commo **conjunto de instancias**.


# Label set
?
- Conjunto de etiquetas, para los ejemplos de clasificación se suele simplificar a: $\{-1,1\}$ o $\{1,0\}$ 


# Trainig data
?
- Representación -> $S=((x_{1},y_{1}),\dots,(x_{m},y_{m}))$
- Secuencia finíta de pares en el conjunto $X \times Y$
- Se puede entender como un conjunto de puntos clasificados del dominio.
- Son los datos a los que el alg. Aprendizaje tiene acceso
- Se les llama también *ejemplos de entrenamiento, Data-points*.

# Salida del algoritmo
?
- Los algoritmos de aprendizaje devuelven una regla de predicción: ==$h:X \rightarrow Y$== 
- A esta función $h$ se le denomina ==predictor, clasificador o **hipótesis**== 
- Esta función será usada para predecir el label de nuevos puntos del dominio que no han sido vistos antes.

# Como se genera un modelo.
?
- Suponemos que los datos son generados bajo una distribución de probabilidad (en este caso representa el entorno donde se generan estos datos)
- Denominamos a esta distribución de probabilidad sobre $X$ como $D$.
- El algoritmo no asume ni conoce en ningún momento nada sobre esta distribución de probabilidad.
- Asumimos que existe una función hipótesis tal que $f:X \rightarrow Y : y_{i}=f(x_{i}) \forall x_{i} \in X$ 

# Medida del error
- *Error del clasificador*::probabilidad de que la función $h$ no prediga de manera correcta un data-point aleatorio generado bajo la distribución de probabilidad $D$ 
- Matemáticamente se expresa como: ![[Pasted image 20230627121902.png]] La medida del error se mide en función de la distribución de probabilidad $D$ y la función objetivo $f$
- A este error se le llama: *generalization-error, riesgo(risk), true error de h*. Se usa la letra L para designar el error ya que se ve como una **perdida (Loss)** del algoritmo.
- 