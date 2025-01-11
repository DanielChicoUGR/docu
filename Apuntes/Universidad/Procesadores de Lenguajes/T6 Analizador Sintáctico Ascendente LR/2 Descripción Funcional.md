La pila del autómata utilizado para el análisis LR está formada por parejas de **símbolos** (terminales y no terminales) y **estados**.

![[Pasted image 20241113121903.webp]]

## Algoritmo

### Como funciona
1. **Si** $\text{acción}[S_m, a_i] = \text{Desplaza}$ **entonces** el analizador inserta en la pila tanto el símbolo de entrada $a_i$ como el siguiente estado $S$ que se obtiene fruto de la evaluación $\text{Goto}[S_m, a_i]$. Ahora, $a_{i+1}$ pasa a ser el símbolo de la entrada a leer y el analizador se encuentra ahora en el estado $S$.$$
   (S_0 X_1 S_1 X_2 S_2 \cdots X_m S_m, a_i a_{i+1} \cdots a_n \$) \rightarrow (S_0 X_1 S_1 X_2 S_2 \cdots X_m S_m a_i S, a_{i+1} \cdots a_n \$)
   $$

2. **Si** $\text{acción}[S_m, a_i] = \text{Reduce}$ **entonces** el analizador ejecuta una reducción utilizando la regla $A \rightarrow \beta$ resultando la siguiente configuración:$$
   (S_0 X_1 S_1 X_2 S_2 \cdots X_m S_m, a_i a_{i+1} \cdots a_n \$) \rightarrow (S_0 X_1 S_1 X_2 S_2 \cdots X_{m-r} S, a_i a_{i+1} \cdots a_n \$)
   $$
3. **Si** $\text{acción}[S_m, a_i] = \text{Acepta}$, el análisis se ha terminado con éxito.

4. **Si** $\text{acción}[S_m, a_i] = \text{Error}$, se ha descubierto un error. El analizador entonces llamará al procedimiento de recuperación de errores.


>[!help]
> ![[Pasted image 20241113122456.webp]]![[Pasted image 20241113122604.webp]]
Donde $S = \text{Goto}[S_{m-r}, A]$ y $r$ la longitud de la cadena de símbolos de $\beta$. Se extraen $2r$ elementos de la pila (estados y símbolos) y después se inserta el símbolo no terminal $A$.

### Pseudocódigo

```
Hacer que p apunte al primer símbolo de w$;
repeat
    Sea S el estado situado en la parte superior de la pila;
    Sea a el símbolo al que apunta p;
    if acción[S, a] = Desplaza S' then
        Cargar a y luego S' en la pila;
        Hacer que p apunte al siguiente símbolo;
    else if acción[S, a] = Reduce A → β then
        Sacar de la pila 2|β| símbolos de la pila;
        Sea S' el estado situado en el tope de la pila;
        Cargar A y el resultado de goto[S', A] en la pila;
        Ejecutar las acciones semánticas de A → β;
    else if acción[S, a] = Aceptar then
        return;
    else
        error();
    end if
until forever
```

>[!example]
>![[Pasted image 20241113124041.webp]]

