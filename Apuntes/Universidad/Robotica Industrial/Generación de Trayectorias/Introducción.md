
> [!info] trayectoria
> Historial en el tiempo fr ls posición, velocidad y aceleración para cada grado de libertad

Generalmente, el usuario especifica la posición y orientación inicial y final del efector y el sistema calcula la forma exacta de la ruta para llegar ahí, la duración, el perfil de velocidad ...

Definir una trayectoria implica definir una función (matemática) para cada dimensión del espacio y cuya variable independiente sea temporal.

# Restricciones a Especificar Por El Usuario:
- Espaciales:
	- En caso de requerir especificar con detalle el movimiento. En estos casos se usan puntos vía
- Temporales:
	- El usuario puede especificar tiempos de respuesta máximos para el destino y/o puntos vía
- De uniformidad:
	- Se refiere a que la trayectoria no tenga ni giros ni cambios de velocidad bruscos con el objetivo de reducir no solo los daños externos sino la durabilidad del los componentes del robot

# Función Uniforme:
?
función continua y cuya primera derivada es continua. Algunas veces es conveniente que la segunda derivada también sea continua.

# Espacios De Las Trayectorias
- ==Espacio Cartesiano(tarea)==:
	- Se refiere a los ejes de coordenadas como los conocemos
	- Genera trayectorias más "lógicas" para el usuario
	- Permiten trayectorias en linea recta en el espacio cartesiano
	- incrementa la carga computacional (resolver el [[Modelo cinemático inverso]] en cada instancia ) 
- ==Espacio de las articulaciones (robot)==:
	- Reduce la complejidad y la carga computacional
	- EL espacio de trabajo es tenido en cuenta de manera implícita 
		- El dominio de las variables articulares se restringe a propósito
		- EL [[Modelo cinemático inverso]] no tiene solución
	- Evita las singularidades fácilmente
	- Puede dar lugar a trayectorias extrañas desde el punto de vista del usuario, incluyendo orientaciones arbitrarias (Esto podría suponer un problema dependiendo de la tarea)
	- Puede generar aceleraciones cartesianas excesivas que den lugar a fuerzas de inercia que dañen los componentes
	![[Pasted image 20230601123629.png]]
	