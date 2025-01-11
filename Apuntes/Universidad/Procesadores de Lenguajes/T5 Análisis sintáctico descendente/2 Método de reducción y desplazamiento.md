
>[!def] 
>Se basa en una máquina con pila donde:
>- El **alfabeto de la pila** está formado por los símbolos terminales y no terminales.
>- El **alfabeto de entrada** está formado por los símbolos terminales
>- La **función de transición** que se define en base a las siguientes acciones sobre la pila:
>	- *Desplazar*
>	- *Reducir*
>	- *Aceptar*
>	- *Error*

Se parte de la subcuencia de símbolos de la entrada. El proceso de análisis consiste en ir explotando el tope de la pila y los elementos siguientes en la pila hasta encontrar una subcadena $\tau$ que coincida con la parte derecha de una producción dada $A \rightarrow \tau$.

Si se encuentra $\tau$ en la pila, entonces se sustituye $\tau$ por $A$ en el tope de la pila. A este proceso se le denomina **reducción**. Y el proceso de pasar símbolos de entrada al tope de la pila se llama **desplazamiento**.

 >[!warning] **Problemas**
 >- Existe mas de una producción para aplicar reducción (*conflicto reduce/reduce*)
 >- Incertidumbre sobre si es posible aplicar desplazamiento en vez de reducción(*conflicto desplaza/reduce*)
> 	- Siempre es posible aplicar desplazamiento, ampliando las posibles subcadenas en el tope de la pila susceptible de ser reducidas en base a un mayor número de producciones.

>[!example]
>![[Pasted image 20241112121735.webp]]

