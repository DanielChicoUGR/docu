==**[[Modelo]] que define la estructura de un [[Lenguaje de modelado (ML)]]**==

1. **Relacion `ElementOf`**
	- Un ML es un conjunto de modelos
2. **Relacion `Defines`**
	- Un ML es definido por un metamodelo
3. Un metamodelo es un **modelo de modelos**
4. **Relacion `ConformsWith`**
	- Un modelo se ajusta a un metamodelo, debe satisfacer las reglas definidas al nivel de su metamodelo

![[Pasted image 20240620234330.png]]

## Motivos de uso
- **Especificación del lenguaje**. 
	- ==Todas las partes interesadas pueden entender un modelo y rebatirlo== si el significado de cada elemento del modelo esta bien especificado
- **Comunicación acerca de los modelos**
	- ==Se simplifica la comunicación entre las partes interesadas==
- **Funciones de mapeo**
	- ==Facilita pasar de un modelo a otro==