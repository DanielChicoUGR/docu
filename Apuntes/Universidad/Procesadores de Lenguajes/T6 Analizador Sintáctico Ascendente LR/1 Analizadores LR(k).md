Surgen como alternativa a los problemas que presentan las restricciones de gramáticas $LL(n)$ para análisis descendente y las gramáticas de precedencia de análisis ascendente. En el siguiente ejemplo se ilustra el problema del error de reducción en análisis de precedencia simple.

Es el método más general y el más usado. 
- **L** - Analiza los símbolos de la entrada de izquierda a derecha (left-right) 
- **R** – Reduce a la derecha (right). 
- **k** – Número de símbolos de anticipación de la entrada. 
 
La confección de la tabla de análisis es algo más compleja que en los métodos predictivos presentados con anterioridad, si bien, resulta muy mecánica la forma de obtenerla. Existen tres técnicas para la confección de la tabla de análisis. Cada una de ellas caracteriza a tres tipos de gramáticas LR que son: 
1. **LR Simple (SLR)**: Es la más fácil de implantar pero la menos potente. 
2. **LR Canónica o LR(1)**: Es la más potente pero la más compleja. 
3. **LALR (LR con anticipación o look-ahead)**: Es la técnica intermedia y más usada. Se trata de una simplificación del método general LR(1) y usado en las implementación de los generadores de analizadores sintácticos basados en YACC.

 ![[Pasted image 20241113121633.webp]]
La técnica de análisis LR es válida para gramáticas de contexto libre no ambiguas


## Ventajas de los analizadores LR(k) 
1. Puede reconocer virtualmente todos los lenguajes que obedecen a una gramática libre de contexto. 
2. Es el método conocido más general sin retroceso, así como el más fácil de implementar de los conocidos de Reducción y Desplazamiento. 
3. Las clases de gramáticas que pueden analizarse mediante el analizador LR son el superconjunto de las gramáticas que pueden analizarse por analizadores predictivos. 
4. El analizador LR puede detectar errores conforme se realiza el análisis, así como aplicar recuperación del análisis con pérdida controlada.