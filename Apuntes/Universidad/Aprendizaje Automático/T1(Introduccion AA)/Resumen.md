
> [!hint] Leyenda
> - D -> Data Domain
> - T -> Transformación realizada a los datos
> - $f$ -> Función que une los dominios T a L (etiquetas) 
> - GT -> Ground Truth (Verdad Absoluta) en el contexto se refiere a elegir la etiqueta correcta

# Aprendizaje Supervisado:
?
- Trasnsformación de los datos de entrada: $T:D \rightarrow R$
- Minimizar el error en el mapeo de etiquetas $f:D \rightarrow R\rightarrow L$ (GT-Labels)
\

# No Supervisado (unsupervised)
?
- Transformación de los datos de entrada: $T:D \rightarrow R$
	- Descubrir nuevas Distancias de los datos (encontrar patrones geométricos?)

# Auto-Supervisado
- Transformación de los datos de entrada $T:D \rightarrow R$
- Minimizar el error en el mapeo de etiquetas $f:D \rightarrow R\rightarrow L$ (Etiquetas de los datos)
- Etiquetas sencillas no relacionadas con ninguna tarea en específico