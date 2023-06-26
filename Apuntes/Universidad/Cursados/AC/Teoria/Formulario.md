- Tema 1
    - Tiempo CPU
        - $CiclosPrograma * T_{ciclo}$ 
        - $CiclosPrograma \div Frecuencia_{CPU}$
        - $NI*CPI*T_{ciclo}$ 
            - NI⇒Numero de instrucciones
            - $NI=N_{oper} \div OP_{instr}$
                - $N_{oper}$⇒Nº de operaciones que realiza el programa
                - $OP_{instr}$⇒ Nº de operaciones por instrucción 
    - Cantidad de ciclos:
        - CP→Ciclos programa:
            - $\sum CPI_i * I_i$  
                - $I_i$⇒ Cantidad de instrucciones del tipo i
                - $CPI_i$⇒ Cantidad de ciclos que tarda en ejecutarse una instrucción del tipo i 
        - CPI→Ciclos por isntrucción.
            - $CPI=CP \div NI$ 
            - $CPI=CPE/IPE$
                - CPE→Ciclos por emisión (Nº mínimo de ciclos transcurrido entre los instantes en el que el procesador puede emitir instrucciones)
                - IPE→Instrucciones por emisión(cantidad de instrucciones que pueden emitirse a la vez cada vez que se realiza una emisión de instrucciones.
    - $T_{ciclo}=1\div Frec_{cpu}$  
    - Ganancia:
        - $$S_p=V_p\div V_1 = T_1 \div T_p$$ 
            - $V_p$  ⇒ Velocidad después de mejora
            - $V_1$ ⇒ Velocidad antes de mejora
            - $T_1$ ⇒ Tiempo antes de la mejora
            - $T_p$ ⇒ Tiempo después de la mejora
    - Productividad:
        - $$P(n)=n\div T_p(n)$$
    - Ley de amdahl
        - La ganancia del tiempo de ejecución en un código viene determinada por una cota superior:
        - $$s \leq p \div (1+f(p-1))$$
            - p ⇒ factor de mejora (si una instruccion se ejecuta en x del tiempo inicial, la mejora es $(x)^{-1}$
            - f ⇒ Fracción del tiempo de ejecución en el que no se aplica la mejora en el código.
- Tema 2 
    - Ganancia en prestaciones:
        - $$S(p)=prestaciones(p) \div prestaciones(1) = T_s \div T(p)$$ 
        - $T_s$⇒ Tiempo ejecución en secuencial
        - $T(p)$⇒ Tiempo de ejecución con p procesadores en paralelo. 
    - Tiempo ejecución en paralelo:
        - $$T_p(p,n)=T_c(p,n)+T_0(p,n)$$
            - $T_c(p,n)$⇒ Tiempo que tarda en ejecutarse la parte en paralelo
            - $T_0(p,n)$⇒ Tiempo que tarda en ejecutarse la parte en secuencial 
- Tema 3
- Tema 4 
- 