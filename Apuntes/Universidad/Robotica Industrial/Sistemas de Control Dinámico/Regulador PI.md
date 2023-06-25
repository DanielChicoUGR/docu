## Regulador PI ($q_p(s)$)
Regulador proporcional integral $R(s)=K_p+\frac{K_i}{s}$ 

### En ausencia de perturbaciones, $\tau_p=0$, ante una petición $q_d=1$ (escalón unitario) 
$$
q(s)=q_c(s)=\frac{K(K_p+\frac{K_i}{s})}{(Js+B)s+K(K_p+\frac{K_i}{s})} * \frac{1}{s}


$$
- En régimen permanente ($t \rightarrow \infty$):  $$  q_p(s)=\frac{sKK_p +KK_i}{(Js+b)s^2+sKK_p +KK_i}=\frac{KK_i}{KK_i}=1$$
-  Tras el tiempo suficiente: q(s)=$q_d$=1
![[Pasted image 20230603193226.png]]

### Perturbación del tipo $\tau_p(s)=\frac{1}{s}$ 

$$  q_p(s)=\frac{-\tau_p}{(Js+B)s+K(K_p+\frac{K_i}{s})}=\frac{-\frac{1}{s}}{(Js+B)s+K(K_p+\frac{K_i}{s})}$$
 - En régimen permanente ($t \rightarrow \infty$):  $$\lim_{t \rightarrow \infty}{\vartriangle q(t)}=
  \lim_{s \rightarrow 0}{sq(s)}=
  \lim_{s \rightarrow 0}\frac{-\frac{1}{s}}{(Js+B)s+K(K_p+\frac{K_i}{s})}=
  0$$![[Pasted image 20230603192455.png]]
  