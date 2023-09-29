# Regulador P ($q_p(s)$)
- Regulador proporcional: $R(s)=K_p$ 
## En Ausencia De Perturbaciones, $\tau_p=0$, Ante Una Petición $q_d=1$ (escalón unitario)
$$
  q(s)=q_c(s)=\frac{KK_p}{(Js+B)s+KK_p}=\frac{KK_p}{KK_p}=1
  $$
- En régimen permanente (t $\rightarrow \infty$):$$
  \lim_{t \rightarrow \infty}{\vartriangle q(t)}=\lim_{s \rightarrow 0}{sq(s)}=\lim_{s \rightarrow 0}\frac{KK_p}{(Js+B)s+KK_p}=\frac{KK_p}{KK_p}=1
  $$
- Tras el tiempo suficiente: q(s)=$q_d$=1
![[Pasted image 20230603191359.png]] Tras el tiempo suficiente, si no hay perturbaciones, se corrigen los pequeños fallos a la hora de ajustar la posición con los motores

## Perturbación Del Tipo $\tau_p(s)=\frac{1}{s}$
$$
  q_p(s)=\frac{-\tau_p}{(Js+B)s+KK_p}=\frac{-\frac{1}{s}}{KK_p}
  $$

- En régimen permanente (t $\rightarrow \infty$):$$
  \lim_{t \rightarrow \infty}{\vartriangle q(t)}=
  \lim_{s \rightarrow 0}{sq(s)}=
  \lim_{s \rightarrow 0}\frac{-\frac{1}{s}}{(Js+B)s+KK_p}=
  -\frac{1}{KK_p}
  $$
- Tras el tiempo suficiente: q(s)=$q_d$=1
![[Pasted image 20230603191451.png]]
Cuando existen perturbaciones este regulador es muy simple y no es capaz de terminar de ajustar la posición cuando hay pares perturbadores externos