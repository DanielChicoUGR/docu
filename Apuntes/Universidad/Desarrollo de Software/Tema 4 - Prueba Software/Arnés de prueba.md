**Colección de software y datos de prueba usados por desarrolladores para realizar [[Pruebas de unidad|pruebas de unidad]]**, simulando una pequeña parte del entorno en el que el software funcionara.

Mediante:
- El uso de controladores ficticios (***mocks***) que hagan una [[Verificación|verificación dinámica]], es decir, prueben el comportamiento (la interacción con otro software *-[[Pruebas automatizadas|pruebas de interacción]] o [[Prueba de caja negra|pruebas de caja negra]]-*) 
- El uso de silenciadores (***stubs***) que hagan una [[Verificación|verificación estática]] (*-[[Pruebas de unidad|pruebas de unidad]] o [[Prueba de caja blanca|pruebas de caja blanca]]-*), es decir, comprueben el estado, silenciando u apagando (*stub out*) toda la parte del código que no se desee probar

[[Diferencias entre mocks y stubs]]

Usan además una librería de pruebas para generar los informes

**Componentes:**
- Librería de test
- Controlador de silenciadores
- Generador de reportes
- Test a ejecutar