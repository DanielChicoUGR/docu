La **matriz Jacobiana** permite relacionar las velocidades de las coordenadas articulares y las de la posición y orientación del extremo del robot
- Es un modelo diferencial $\rightarrow$ Estudia el efecto que un movimiento diferencial de las variables articulares tiene sobre las variables en el espacio de la tarea
- Forma parte del análisis cinemático del manipulador
- El Sistema de control del robot usa la *matriz Jacobiana* para determinar qué velocidades debe asignar a cada articulación (a través de sus respectivos actuadores) para que el extremo se mueva en una trayectoria concreta a la velocidad deseada.

**Distinguimos entre:**
?
- [[Jacobiana analítica]] $\rightarrow$ Relación de las **velocidades articulares ($\dot{q_1},\dot{q_2},\dots,\dot{q_n}$)con las velocidades de la localización del extremo del robot, siendo esta la posición y orientación expresada en base a sus coordenadas cartesianas y a sus ángulos de Euler ($\dot{x},\dot{y},\dot{z},\dot{\alpha},\dot{\beta},\dot{\gamma}$)**.
- [[Jacobiana geométrica]] $\rightarrow$ Relación de las **velocidades articulares ($\dot{q_1},\dot{q_2},\dots,\dot{q_n}$) con los vectores de velocidad linear y angular ($v_x,v_y,v_z,w_x,w_y,w_z$)** con que se mueve el extremo del robot.

