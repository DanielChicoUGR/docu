Los controladores ficticios (*mocks*) y los silenciadores (*stubs*), son considerados dos tipos de los llamados *dobles de prueba*

| *Mocks*                                                                                            | *Stubs*                                                                                       |
| -------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| **Llamados por** la clase testeada                                                                 | **Proporciona informacion** a la clase y al objeto testeado                                   |
| Prueban si una clase hace lo que es requerido por una dependencia. Verifican el **comportamiento** | No da detalles sobre como la clase usa una dependencia. Verifican el **estado**               |
| Implementan la interfaz y la dependencia                                                           | Implementan métodos abstractos de forma que devuelven el valor necesario para hacer la prueba |
| Pueden provocar un fallo del test                                                                  | No pueden provocar un fallo del test                                                          |
