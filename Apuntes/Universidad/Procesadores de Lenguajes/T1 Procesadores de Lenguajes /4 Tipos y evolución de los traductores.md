## Evolución de los lenguajes de programación

```mermaid
flowchart TB

1["`Lenguaje Máquina`"]
1_1["`1.Direcciones de memoria
2.Operaciones Aritmético-lógicas
3.Registros de acumuladores
4.Copia de datos entre registros y direcciones de memoria
5.Control de flujo`"]
2["`L. Funcionales`"]
3["`L. Lógicos`"]
4["`Nemotécnicos`"]
4_1["`1.Direcciones Simbólicas
2.Macros`"]
13["`L. Ensamblador`"]
5["`Lenguajes de entorno algebraico`"]
5_1["`1.Variables
2.Expresiones Aritméticas
3.Tipos Elementales
4.Arrays
5.Subprogramas`"]
6["`Lenguajes Traductores de formulas`"]
7["`Programación estructurada`"]
7_1["`1.Tipos Estructurados
2.Declaraciones explicitas
3.Variables Locales y Globales
4.Anidamiento
5.LLamadas recursivas
6.Memoria Dinámica
7.Llamadas por nombre,valor-resultado, referencia`"]
8["`Lenguajes estructurados en Bloques`"]
9["`Sincronización y comunicación`"]
10["`Lenguajes Paralelos`"]
11["`Tipos de datos abstractos`"]
11_1["`1.T.D.A.
2.Clases
3.Herencia
4.Polimorfismo
5....`"]
12["`Lenguajes Orientados a objetos`"]

1-->2
1-->3
1-->4
1-.->1_1
4-->13
4-.->4_1
13-->5
5-->6
5-.->5_1
6-->7
7-->8
7-.->7_1
8-->9
9-->10
8-->11
11-->12
11-.->11_1

```
![[4 Tipos y evolución de los traductores-20241105114422110.webp]]


## Evolución de los traductores

## Compiladores

>[!important]
>Los compiladores obtienen una especificación en lenguaje máquina equivalente a la del lenguaje original
 
![[Pasted image 20241105115738.webp]]

La fase de compilación se puede dividir en:
**Compilación**::Traduce la especificación de entrada a lenguaje máquina incompleto y con instrucciones máquina incompletas.
**Enlazador**::Enlaza los programas objetos y completa las instrucciones máquina incompletas, generando un ejecutable.
## Intérpretes

>[!important]
>Un intérprete carga la especificación de un programa en lenguaje no máquina y la interpreta y ejecuta, instrucción a instrucción.

![[Pasted image 20241105115929.webp]]

