Tienen el cometido de descubrir **errores asociados a la interfaz o interactuación entre [[Prueba de componentes|componentes]]**

Frente al enfoque big-bang, solo recomendable en sistemas pequeños, el enfoque mas usado para probar sistemas grandes cuyos distintos componentes se van terminando de desarrollar en distintos momentos es el *enfoque incremental*

Existen dos formas de realizar pruebas con un enfoque incremental:
- **Top-down**. 
	- Se prueban los componentes empezando por el nivel mas alto de la jerarquía (main) y terminando por probar otros componentes a nivel mas bajo. Para probar un componente de un nivel se usan *stubs* que reemplazan a los componentes de nivel inferior. Una vez que se prueba un componente, se utiliza dicho componente para probar los de nivel inferior
- **Bottom-up**.
	- Se comienza construyendo y probando primero módulos atómicos, es decir, componentes en los niveles mas bajos de la estructura del programa, eliminando, de esta forma, la necesidad de crear *stubs* en la estructura de la prueba de integración