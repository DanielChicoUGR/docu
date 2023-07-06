*solución PAC*:: Solución  Probablemente Aproximadamente Correcta -> Devuelve una aproximación con una alta probabilidad de que sea correcta.

Para explicar las herramientas usadas, se usará la [[Analogia de la papelera]]
De esta analogía extraemos en claro la siguiente inecuación: $P(|\%\text{verdes}_{muestra} - \%\text{verdes}_{bolsa}| < \epsilon) \leq 2*e^{-2*\epsilon^2*N}$
## Aplicación de la inecuación de Hoeffding al ML
Cada canica es un ejemplo de la población, con sus características, están serán verdes o rojas en función si para esa hipótesis h, clasifica correctamente el ejemplo o no.
Traducidos al ML los parámetros serian:
- $\%\text{rojas}_{muestra} \rightarrow E_{in}$  
- $\%\text{rojas}_{bolsa} \rightarrow E_{out}$
Esta incecuación es valida sólo para una hipótesis, es decir $|H|=1$ y con una hipótesis $h$ elegida sin ver los datos.
