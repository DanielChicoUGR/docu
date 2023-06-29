*Normalización*::Proceso de hacer que todos los inputs estén en la misma escala.

## Cálculo
Si los datos se encuentran centrados, una buena manera de normalizar (llevarlos todas las características a la misma escala) sería a través de la desviación standard/Dispersión de la característica definida por: $$\sigma^{2}_{i}=\frac{1}{N} \sum^{N}_{n=1}x^{2}_{n,i}$$ Con i siendo la componente numero i de los datos.


Para obtener la transformada dividimos cada característica i con el $\sigma_{i}$ correspondiente.

Esto se puede representar como $z_{n}=D \times x_{n}$ siendo $D$ una matriz diagonal con el elemento $D_{i,i}=\frac{1}{\sigma_{i}}$ 