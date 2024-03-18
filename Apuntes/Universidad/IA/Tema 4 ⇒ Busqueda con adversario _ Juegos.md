- Juegos bipersonales con información perfecta
    - Estas situaciones se estudian y resuelven utilizando la Teoría de juegos.
    - Juego→Es cualquier situación de decisión, caracterizada por poseer una interdependencia estratégica, gobernada por un conjunto de reglas y con un resultado bien definido.
    - En un juego, cada jugador intenta conseguir el mayor beneficio para su interés.
- Árboles de ecxploración de juegos
    - Un árbol del juego es una representación explicita de todas las formas de jugar a un juego
    - Existe una correspondencia entre los árboles Y/O y los aárboles de juegos.
    - Notación min/max
        - **MAX⇒ **primer jugador
        - **MIN⇒ **segundo jugador
        - **Nodos MAX y nodos MIN**
        - Los nodos **TERMINALES **se etiquetan con **V, D o E **desde el punto de vista de **MAX**
            - V⇒ Victoria
            - D⇒ Derrota
            - E⇒ Empate
        - **EJEMPLO:**
            - ![](https://remnote-user-data.s3.amazonaws.com/fXSBvfMLXi2TCRzSQoAPclUgK5CKvw0DTvAwC6DCOexdmPwM05-bkpNlcMLDyM_HMJqXA7B0coHtXUyE0DV0Q5JTxuhNuISZ5Mu_4fXVKsCgR6ra85vBtLbIepRH0jcs.png) ![](https://remnote-user-data.s3.amazonaws.com/1Ky9peHOyVp6hQdaC7kSpbkmlbiDpYUzFXeeK19KrNuz6PP4_U9VZElJIJn4KoXKQgdXBhaVre7vhe905kIgSt40x1PfoNL_s6E8RrV9p9Qp3vXEj9x6v4TB9rBOADY6.png) 
        - Algoritmo Status(J)
            - Nodo MAX:
                - V⇒ si alguno se sus sucesores tiene Status=V
                - D⇒Si todos los sucesores tienen Status D
                - E⇒ En otro caso
            - Nodo MIN
                - V⇒ Si todos los sucesores tienen Status V
                - D⇒ Si alguno de los sucesores tiene Status D
                - E⇒ En otro caso
        - 
    - Juegos Complejos:
        - los juegos complejos no se pueden resolver ya que es imposible explorar todo el arbol de estados hasta la terminación
        - Nuevo objetivo ⇒ Encontrar La mejor jugada inmediata
        - Importancia de las heurísticas
- El modelo básico
    - La regla min_max ↓ 
        - El valor de V(j) de un nodo de la frontera es igual a su evaluación estática de la función heurística. En otro caso:
        - J⇒ nodo MAX:
v(j)= maximo de los valores de los nodos sucesores
        - j⇒ nodo MIN:
v(j)=minimo d elos valores de sus nodos sucesores
    - pseudocódigo MIN/MAX:
        - ![](https://remnote-user-data.s3.amazonaws.com/s6I-5RWMuOheMZ281wMyx6HbzClXOXjrttBMH2YJV-hXNmHRvQJlGlvhOvZUk7wGn2VP0J5j1YyUugtHxHjxI-ycwL0BaERNIV9cMrwapq4WJ5qCPmF-qzCB-oFF_0it.png) ![](https://remnote-user-data.s3.amazonaws.com/0D5o3qGv7zUG0ka8k7AAnrAoru371dVDV8sawB9sb0oQd4-wMHMeczqhwbiGDya47XwuZ1kBsSOCjPdP-4F2aDbGfO9KG5KWBbfaPNHTl5KK6aoADAnzDcgL_p-ngiGL.png) 
        - Este algortimo explora todos los posibles valores del juego, haciendo el algoritmo bastante ineficiente en tiempo y espacio debido al alto grado de ramificación.
    - Algoritmo alfa/beta:
        - Modificación del algoritmo MIN/MAX con el objetivo de mejorar su complejidad espacial y temporal aplicando podas al arbol de estados.
        - Calculo de Cotas:
            - ![](https://remnote-user-data.s3.amazonaws.com/faOl8amQk96E0EoCZOnwZ7yk1dUDdOPQtdJzYcXIKZgoPjLlCsSLoT4OPtrw4JWIKARTdgQzirJEltRfzBUVFRnohs2dfiUNWhrTV1M3L1gYG86F1AqtMCO8Gdv_h0j-.png) 
        - PsudoCódigo:
            - ```cpp
función alfa-beta(nodo /*en nuestro caso el tablero*/, profundidad, α, β, jugador)
    si nodo es un nodo terminal o profundidad = 0
        devolver el valor heurístico del nodo
    si jugador1
        para cada hijo de nodo
            α := max(α, alfa-beta(hijo, profundidad-1, α, β, jugador2))
            si β≤α
                romper (* poda β *)
        devolver α
    si no
        para cada hijo de nodo
            β := min(β, alfa-beta(hijo, profundidad-1, α, β, jugador1))
            si β≤α
                romper (* poda α *)
        devolver β
        
 //(* Llamada inicial *)
alfa-beta(origen, profundidad, -infinito, +infinito, jugador_deseado)
``` 
- Juegos en los que interviene un elemento aleatorio
- ![](https://remnote-user-data.s3.amazonaws.com/W92AwyCZ1oUSXFOiTPeWe7XT0qPs8dSZ_C3WLsAVisr1W8SZ-wHGBdlIHz0DSgy9lM1tezbJjNBR8xa2rEwQ_7d_qeZ-vCXqpWElOSphhBAqO6H2fNJz3D6vS_slLMDe.png) 
