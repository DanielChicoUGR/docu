- La velocidad de un procesador esta relacionada con las instrucciones por ciclo y la frecuencia. $Vcpu=IPC*F$
- Clasificación de cores Multithread:
    1. **Temporal Multithreading (TMT)**→La conmutación entre threads la decide y controla el hardware. Emiter instrucciones de un unico thread por ciclo.
        - Clasificación cores con TMT
            1. **Fine-grain Multithreading (FGMT) **→La conmutación de hebras la decide el hardware en cada ciclo (coste 0). Procesadores de tipo temporal en la que en cada ciclo puede pasar de una hebra a otra. Funciona por turno rotatorio (Round Robin) o por eventos de cierta latencia.
            2. **Coarse-grain Multithreading (CGMT) **→ 
            - 
    2. **Simultaneous Multithreading (SMT) **→Ejecutan en un cores superescalar varios thread en paralelo. Puede emitir instrucciones de varios thread por ciclo.
- Microarquitecturas [ILP](../../../../ILP.md).Cauces Superescalares
    - ![](https://remnote-user-data.s3.amazonaws.com/sIuU60LhU8ge9igoaQsqNWaAs4wm1If4NIvxBX78Fnp9SzjEF7-s5uIYXByjYmp1NEumeISCeFPDguotlPXis-c2VmoiO7eb1rizFRItxne3Zh1FTITfVIhWWqvizF59.png) ![](https://remnote-user-data.s3.amazonaws.com/uhFqMCF5stzL9vCHgxGaFdG6b-op15tRGjPZjXOw6cs3md_GGVTRUmDV8emI1EGNhkHLx83bVtvrNkPTWMUYEtG483uDo8JseQb2N86Y3M22dzbihgJNRXrsIT1dBnth.png) 
    - Ordenaciones en una secuencia de instrucciones:
        1. Orden de Captación ⇒ orden en que aparecen las instrucciones en el programa y se codifican.
        2. Orden de ejecución ⇒ orden en el cual las instrucciones que se codifican pasan a ejecutarse en un determinado orden.
        - El orden en el que las instrucciones modifican los registros y la memoria modifican el estado interno de la máquina. El procesador superescalar debe ser capaz de identificar el paralelismo entre instrucciones que exista en el programa y organizar la captación, decodificación y ejecución de instrucciones en paralelo.
        - La única restricción es que el resultado del programa sea correcto.
    - Cauces Superescalares
        - Etapas:
        - 
- 
- 
- 
