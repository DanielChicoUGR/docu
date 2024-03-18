- 
- **Anillo Conmutativo**→Sea A un conjunto no vacío, decimos que A tiene estructura de anillo conmutativo sii en A tenemos definidas dos operaciones: ![](https://remnote-user-data.s3.amazonaws.com/N8FD7TU5U_Jte_9yADyRuwvboh9bNt1O8WZYLVEBbXjZr4zEPVc-DqisKUJyhLos1uaofJdF6ZU6Z_2bSimZY_vu0cUHPC_pgm2Z6_ww0N78XdCOAZvlOn-_vhgCMf0u.png)  ⇒Suma y producto respectivamente.
    - Estas Operaciones han de cumplir la siguiemtes propiedades ↓ 
        1. Para cualesquiera a, b, c ∈ A se tiene que (a + b) + c = a + (b + c).
        2. Para cualesquiera a, b ∈ A se tiene que a + b = b + a.
        3. Existe un elemento 0 ∈ A tal que a + 0 = a para cualquier a ∈ A.
        4. Para cualquier a ∈ A existe un elemento b ∈ A tal que a + b = 0.
        5. Para cualesquiera a, b, c ∈ A se tiene que (a · b) · c = a · (b · c).
        6. Para cualesquiera a, b ∈ A se tiene que a · b = b · a.
        7. Existe un elemento 1 ∈ A tal que a · 1 = a para cualquier a ∈ A.
        8. Para cualesquiera a, b, c ∈ A se tiene que a · (b + c) = a · b + a · c
    - Si además, se cumple la propiedad adicional ⇒ Para cualquier a ∈ A, a != 0 existe un elemento b tal que a · b = 1 se dice que A tiene estructura de cuerpo.
    - De manera informal, podríamos decir que un anillo es un conjunto en el que podemos sumar,restar y multiplicar, con las propiedades  usuales respecto a estas operaciones. Si el producto es conmutativo, también se puede dividir salvo por 0
- ^^Polinomios:^^ 
    - Definición→Sea A un **anillo conmutativo,** y $x$ un elemento que no pertene a A. Un polinomio con coeficientes en A es una expresión de la forma: $$a_nx^n+a_{n-1}x^{n-1}+\dots+a_1x+a_0$$ donde $n \in \N$ y $a_k \in A$
    - Los polinomios con coeficientes en un anillo se definen de la misma manera
    - $K[x]$→**conjunto formado por los polinomios con coeficientes en **$K$ 
    - ^^Generalidades de Polinomios:^^ 
        - **Sea **$K$** un cuerpo **$p(x)=a_nx^n+a_{n-1}x^{n-1}+\dots+a_1x+a_0 \in K$** ** 
        1. Si $a_n \neq 0$ entonces se dice que $p(x)$ tiene **GRADO **n.
            - El polinomio $p(x)=0$ no tiene grado. 
        2. Al elemento $a_k \in K$ se le llama **coeficiente de grado k, **y a la expresión $a_kx^k$, t**ermino independiente.** 
        3. El termino de grado n de un polinomio de grado n se le llama **coeficiente lider,** y a la expresión $a_nx^n$ **término lider**.
        4. El coeficiente de grado 0 se llama **termino independiente**
        5. Un polinomio con un coeficiente líder que valga 1 se le llama **polinomio mónico.**
        6. Un polinomio de grado 0, o el polinomio 0 se le llaman **polinomios constantes.** 
    - ^^Operaciones con Polinomios:^^ 
        - ^^Suma^^ 
            - Sean:  $p(x)=a_mx^m+a_{m-1}x^{m-1}+\dots+a_1x+a_0$  y $q(x)=b_nx^n+b_{n-1}x^{n-1}+\dots+b_1x+b_0$ dos polinomios con coeficientes en $K$, Supongamos que $n \le m$, definimos el polinomio suma $p(x)+q(x)$ como:
            - $$p(x)+q(x)=a_mx^m+a_{m-1}x^{m-1}+\dots+a_{n+1}x^{n+1}+(b_n+a_n)x^n+(b_{n-1}+a_{n-1})x^{n-1}+\dots+b_{1}+a_{1}x+(b_0+a_0)$$  
        - ^^Multiplicación ^^ 
            - Sean:  $p(x)=a_mx^ma_{m-1}x^{m-1}+\dots+a_1x+a_0$  y $q(x)=b_kx^k$ dos polinomios con coeficientes en $K$, Supongamos que $n \le m$, definimos el polinomio suma $p(x)*q(x)$ como:
            - $$p(x)*q(x)=a_mx^mb_kx^k+a_{m-1}x^{m-1}b_kx^k+\dots+a_1xb_kx^k+a_0 b_kx^k$$
            - Sean:  $p(x)=a_mx^m+a_{m-1}x^{m-1}+\dots+a_1x+a_0$  y $q(x)=b_nx^n+b_{n-1}x^{n-1}+\dots+b_1x+b_0$ dos polinomios con coeficientes en $K$, Supongamos que $n \le m$, definimos el polinomio suma $p(x)*q(x)$ como:
            - $$p(x)*q(x)=p(x)*q_n(x)+p(x)q_{n-1}(x)+\dots+p(x)q_1(x)+p(x)*q_0(x)$$ 
        - Estas operaciones definidas (suma,producto polinomios en un anillo conmutativo) satisfacen las siguientes propiedades→![](https://remnote-user-data.s3.amazonaws.com/OVkqajLWpePpNwMaCK8vYDN1GO4-KBeoPK8ETZ49yj0fRdI_KgwmihVNCw93886fkOHnhOt4TvgCQ24w53jLQVCaWYXYv9jcEj8IFzlAAfq5U1HkgP3bKvYURAoOLglR.png) 
        - Estas propiedades nos dicen que, si A es un anillo conmutativo, entonces A[x] es también un anillo conmutativo
        - Si A es un cuerpo, A[x] es un anillo conmutativo
        - ^^Evaluar un Polinomio:^^ 
            - Sea $K$ un cuerpo, $p(x)=a_mx^m+a_{m-1}x^{m-1}+\dots+a_1x+a_0 \in K[x]$ y $b \in K$. Definimos la evaluación del polinomio p(x) en x=b (que se denotará como p(a)) como:
$p(b)=a_mb^m+a_{m-1}b^{m-1}+\dots+a_1b+a_0 \in K$ 
            - **Teorema del Resto**→sea $p(x) \in K[x]$ y $a \in K$. Entonces el resto de dividir p(x) entre (x-a) es el resultado de evaluar p(x) en el punto a ⇒ $p(x) \: mod \:(x-a)=p(a)$ 
            - **Teorema del Factor**→sea $p(x) \in K[x]$ y $a \in K$. Entonces a es raíz de p(x) ⇔$(x-a)|p(x)$ 
            - ![](https://remnote-user-data.s3.amazonaws.com/hYHlZ_1bk0Lvp7LN2IO2O3CKk_wHfXjWXF-Dt8zjQGaW7vDvMnn4Ss5VEaE7x7JbAZiypLoAJJaF4frx_sC3R2rPWD6nZnPBQ9CeK94CG2qksR9wf8HtxWWtpQn3bJxP.png) 
- ^^División Polinomios: ^^ 
    - **Teorema Division**→Sea K un cuerpo, y p(x), q(x) dos polinomios de K[x], con q(x) != 0. Entonces existen únicos polinomios c(x), r(x) ∈ K[x] tales que: 
p(x) = q(x) · c(x) + r(x) 
r(x) = 0 o gr(r(x)) < gr(q(x)). 
Los polinomios c(x) y r(x) son llamados cociente y resto respectivamente 
        - $r(x)=p(x) mod q(x)$
        - $c(x)=p(x) div q(x)$ 
        - ^^Propiedades^^ 
            - $p(x) \: mod \:1=0$
            - $p(x) \: mod \: x-a$ = p(a)  ([Teorema del Resto](../ALEM/T2 Cuerpos Finitos/Polinomios_/Operaciones con Polinomios_/Evaluar un Polinomio_/Teorema del Resto.md))
Si $a \in K^*$ entonces $p(x) \: mod \: q(x)= p(x) \: mod \:( a*q(x))$ y $p(x) \: div \: q(x)= a[p(x) \: div \: (a*q(x))]$** **
**IMPORTANTE, AL DIVIDIR, SE INTENTARÁ SIEMPRE QUE EL DIVISOR (q(x))**  **SEA SIEMPRE UN POLINOMIO MÓNICO** 
                - [Un polinomio con un coeficiente líder que valga 1 se le llama polinomio mónico.](../ALEM/T2 Cuerpos Finitos/Polinomios_/Generalidades de Polinomios_/Un polinomio con un coeficiente líder que valga 1 se le llama polinomio mónico.md) 
    - ^^Algoritmo de la división (algoritmo de Horner)^^ 
        - Vamos a calcular el cociente y el resto de dividir p(x) entre q(x). Disponemos los coeficientes como sigue:![](https://remnote-user-data.s3.amazonaws.com/Zti9Y_L4mU24PVU-QWagrU-j9bEtgFS_yIap4RxOpT6ehcDwrsEbJm_9yiHf0g_J6UaVBXHWtT6ri24IKcvxE7qqz7ROy03D44Tb7_-fGt2JYJr-EUxOeqt1skXUyM9t.png) 
            1. Escribir los coeficientes del dividendo en la fila superior con su propio signo. Escribir los coeficientes del dividendo en la fila superior con su propio signo. Se escribe los coeficientes del divisor en una columna a la izquierda: El primero de ellos con su propio signo y los demás con signo cambiado. Se escribe los coeficientes del divisor en una columna a la izquierda: El primero de ellos con su propio signo y los demás con signo cambiado.
            2. El primer término del dividendo se divide entre el primer término del divisor, obteniéndose así el primer término del cociente.
            3. Se multiplica este término del cociente por los términos del divisor a los cuales se cambió de signo, colocándose los resultados a partir de la segunda fila, corriendo un lugar hacia la derecha.
            4. Se reduce la siguiente columna y se coloca el resultado en la parte superior para dividirlo entre el primer coeficiente del divisor y obtener el segundo termino del cociente...
            5. Se continúa este procedimiento hasta obtener el término debajo del último termino del dividendo.
            6. Para obtener los coeficientes del residuo se reducen sumando directamente cada una de las columnas.
        - Ejemplos:
            - ![](https://remnote-user-data.s3.amazonaws.com/nXFBzyGI_qtP6fM5yq6A1VxeLtYF9_PSMpo0jh6KT1FeXu3AW3SNy5Bp4J88qlIgowqurigsFV_t8iBSiM-spihfV4J_cPQL7U0G_4AuhetiD1jTKtW8-17scwrIVxsR.jpeg) 
    - ^^Relacion de Divisibilidad.^^ 
        - Relacion de division en los enteros ⇒[Divisibilidad](../../Cursados/ALEM/T1/Divisibilidad.md)
        - En los polinomios se define de la misma manera:
Sea K un cuerpo y $a(x),b(x) \in K[x]$. Decimos que $a(x)|b(x)$ ⇔ existe $c(x) \in K[x]$ tal que $b(x)=a(x)*c(x)$ 
        --------------------- Portal ---------------------
            - Universidad
    - MCD y MCM de polinomios.
        - Se definen de la misma manera que en los numeros enteros y tiene unas propiedades similares
    - ^^Polinomios Irreducibles^^ 
        - **Definición**→Sea K un cuerpo, y sea $q(x) \in K[x]$ no constante. Decimos que q(x) es irreducible ⇔ sus únicos divisores son polinomios constantes no nulos  y polinomios de la forma: $\lambda * q(x) : \lambda \in K^*$
            - El equivalente a los numeros Primos en $\Z$, donde la unidad son polinomios constantes no nulos, y el mismo son los polinomios de la forma: $\lambda * q(x) : \lambda \in K^*$
        - **Teorema Factorización de Polinómios (**[Teorema Fundamental de la Aritmética](../../../Teorema Fundamental de la Aritmética.md)** en polinomios)**
            - Sea K un cuerpo y $q(x) \in K$ (mónico). Entonces q(x) se escribe de forma única (salvo modificación de orden) como producto de polinómios irreducibles (mónicos)
        - Todos los polinomios de grado 1 son irreducibles 
        - Un polinómio q(x) tiene un divisor de grado 1 ⇔ tiene una raíz. De hecho $(x+a)|q(x)$⇔ $q(-a)=0$ ([Teorema del Resto](../ALEM/T2 Cuerpos Finitos/Polinomios_/Operaciones con Polinomios_/Evaluar un Polinomio_/Teorema del Resto.md)) 
        - **Si **$gr(q(x))=n$** y es reducible, entonces tiene al menos un divisor cuyo grado**$\le  \frac{n}{2}$ ^^⇐IMPORTANTE^^ 
        - Polinomios irreducibles en:
            - $\Complex[x]$
                - Solo los polinomios de grado 1 son irreducibles
            - $\R[x]$
                - Los polinomios de grado 1 son irreducibles
                - Los polinomios de grado dos con discriminante negativo son irreducibles
            - $\mathbb Q[x]$
                - Para cualquier número natural $n\ge1$ hay polinomios irreducibles de grado n
            - $\Z_p[x]$
                - Para cualquier número natural $n\ge1$ hay polinomios irreducibles de grado n  
    - Algoritmo de Euclides (extendido)
        - El calculo del mcd con el algoritmo de euclides, incluyendo su versión extendida parten de los mismos componentes teóricos que al aplicarlo en los enteros (tiene sentido).
- Cuerpos Finitos
    - Anillos cocientes de Polinomios:
        - Sea K un cuerpo, $a(x),b(x),m(x) \in K[x]$ y $gr(m(x))\ge1$.
        - Decimos: $a(x) \equiv b(x) \mod m(x)\rightarrow m(x)|b(x)-a(x)$.
            - Es equivalente a decir ($a(x) \equiv b(x) \mod m(x)\rightarrow  a(x)\mod m(x)=b(x)\mod m(x)$(dan el mismo resto al dividirlo por m(x).
        - **Es una relación de equivalencia (reflexiva, simétrica y transitiva)**
            - $$[a(x)]_{m(x)}=\{b(x) \in K[x] : a(x) \equiv b(x) \mod m(x) \}$$ Todos los polinomios que son congruentes con a(x) modulo m(x)
        - $K[x]_{m(x)}=\{[a(x)]_{m(x)}:a(x)\in K[x]\}$⇒ Conjunto de las clases de equivalencia modulo m(x).
