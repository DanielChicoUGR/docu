```ad-hint
title: Significado de Whitening
Término extraido del procesamiento de señales donde una onda de ruido blanca es una onda con su espectro de frecuencia distribuido de manera uniforme.
```

*Input whitening*::Proceso de descorrelacionar los datos unos de otros para que las relaciones entre los mismos no genere problemas en el proceso de aprendizaje.

## Cálculo:

### PreTransformación:
$$\Sigma=\frac{1}{N}\sum^{N}_{n=1}x_{n}x_{n}^{T}=\frac{1}{N}X^{T} \times X$$
-  $\Sigma \to$ Covarianza entre $i,j$. Si i=j -> Varianza característica i -> $\sigma^{2}$ 

### Transformación:
$$z_{n}=\Sigma^{-\frac{1}{2}}x_{n}$$
A cada característica de los datos ha de multiplicarla por la inversa de la raiz cuadrada de la matriz de Varianza













[[]]