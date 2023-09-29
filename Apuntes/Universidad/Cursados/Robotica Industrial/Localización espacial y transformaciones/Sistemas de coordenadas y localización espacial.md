# Sistemas De Coordenadas
La manipulación robótica implica el desplazamiento de piezas, herramientas y/o objetos en el espacio.
A los *Sistemas de Coordenadas (SC)* se les conoce también como *tramas*

Usaremos Sistemas de coordenadas:
?
1. Ortogonáles -> Ejes perpendiculares entre sí
2. Normalizados -> Los ejes están definidos por vectores de módulo 1
3. Destrógiros -> Cumple la regla de la mano derecha para el producto vectorial
<!--SR:!2023-05-10,3,250-->

# Posición Y Orientación En El Espacio

Toda posición en el espacio queda definida por:
?
1. Sistema de coordenadas de referencia
2. Un vector de coordenadas de la dimensión del espacio (Al trabajar en el mundo real $R^3$ )
<!--SR:!2023-05-10,3,250-->

## Tipos De Ejes
### Coordenadas Cartesianas:

$^AP=\begin{bmatrix} p_x \\ p_y \\ p_z \end{bmatrix}$ :![[Pasted image 20230425124636.png]] Punto p sobre la Trama (ejes de coordenadas A)

### Coordenadas Cilindricas: $(r,\theta,Z)$
![[Pasted image 20230425125109.png]]

### Coordenadas Esféricas: $(r,\alpha,\beta)$
![[Pasted image 20230425125316.png]]

## Representación De la Orientación

Toda orientación en el espacio queda definida por:
?
 Sistema de coordenadas de referencia
 Matriz de Rotación/Ángulos/otros
<!--SR:!2023-05-10,3,250-->

Es habitual adjuntar un SC al punto de forma que el SC define la orientación del punto.
La orientación viene dada por la diferencia entre la orientación del SC asociado al punto y el SC de referencia.

### Matrices De Rotación
Los elementos de la matriz de rotación son proyecciones de los vectores unitarios que definen un SC en los de otro SC
![[Pasted image 20230425131449.png]]

![[Pasted image 20230425131556.png]]
```ad-important
Las operaciones se aplican de derecha a izquierda
```
