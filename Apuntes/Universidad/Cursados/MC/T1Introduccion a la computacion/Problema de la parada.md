## Indice 
- [[#Qué puede ser resuelto de forma automática?|Qué puede ser resuelto de forma automática?]]
	- [[#Qué puede ser resuelto de forma automática?#Ejemplos de problemas indecidíbles|Ejemplos de problemas indecidíbles]]
- [[#Problema de la parada|Problema de la parada]]
	- [[#Problema de la parada#Demostración|Demostración]]
- [[#Otras Definiciones|Otras Definiciones]]

## Qué puede ser resuelto de forma automática?
**Decibilidad**:: Área de estudio centrada en qué puede resolver una computadora
Los problemas que puede resolver una computadora se denominan decidíbles

### Ejemplos de problemas indecidíbles
- Problema de la parada
- Determinar si una gramática sin contexto genera todas las cadenas posibles, o si es ambigua
- Dadas dos gramáticas sin contexto, determinar si generan el mismo conjunto de cadenas, o si se genera un subconjunto de las cadenas generadas por el otro, o si hay alguna cadena en absoluto que ambos generan
- [La existencia de una brecha espectral de un materia cuántico](https://www.abc.es/ciencia/abci-problema-fisica-no-puede-resolver-201512101033_noticia.html) 
## Problema de la parada 
```ad-question
Dado un programa p y sus datos de entrada x, decidir si p eventualmente terminará en un número finito de pasos
```

```ad-danger
title: IRRESOLUBLE
```

### Demostración
Supongamos el siguiente programa

```pseudo
	\begin{algorithm}  
	\begin{algorithmic}
	\Procedure{Termina}{$P,x$} 
		\If{\Call{Para}{\Call{P}{x}}} 
			\Return \True 
		\Else
			\Return \False
	  \EndIf 
	\EndProcedure 
	\Procedure{Para}{$w$} 
		\If{\Call{Termina}{w,w}}
			\While{\True}
			\EndWhile
		\EndIf
	\EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

La función Para sale si el programa no acaba, Pero esto genera la contradicción de que el programa parará si el programa para no para ????? 


## Otras Definiciones

**Tratabilidad**::Área de estudio que estudia que puede resolver una computadora de manera eficiente.
**Problema Tratable**:: Problema que una computadora puede resolver en tiempo proporcional a una función que crece lentamente en relación con el tamaño de al entrada.
**Gramática**:: Modelos útiles en el diseño de software que sirve para procesar datos con una estructura recursiva.
**Expresiones regulares**::Especifican la estructura de los datos, especialmente de las cadenas de texto.