- Que es?
    - Definición→Algoritmo de cifrado consistente en dos claves (una pública y otra privada)
Cuando se quiere enviar un mensaje, el emisor busca la clave públican del receptor. Una vez que el mensaje cifrado llega al erceptor. Este usa su clave privada para descifrar el mensaje.
- Como se usa.
    1. Escogemod dos numeros primos: 
        - p⇒461
        - q⇒ 919
    2. Se calculam:
        - $n=p*q$
            - $n=461*918=423659$ 
        - $\varphi(n)=(p-1)(q-1)$ 
            - $\varphi=(641-1)*(919-1)=422280$ 
    3. Se busca un numero e (impar) que sea primo relativo a $\varphi(n)$, ($1<e<\varphi$) se selecciona un entero aleatorio que cumpla esas condiciones. 
        - e=37
    4. Se calcula $d$ el coeficiente de Bezout de $e$ en tras aplicar el [Algoritmo de Euclides: ](../../Cursados/ALEM/T1/Divisibilidad/Algoritmo de Euclides_.md) (e,$\varphi(m)$) 
        - d=11413
- Resultado:
    - Claves públicas:
        - n
        - e
    - Clave Privada
        - 11413
- Cifrado:
    - C ⇒Mensaje cifrado
    - M⇒ Mensaje(informacion) sin cifrar
    - $$C=M^e mod\ n$$ 
    - El usuario que cifra solo debe conocer el los dos valoeres de clave pública.
- Descifrado:
    - $$M=C^dmod\ n$$
    - el usuario que descira conoce todos los valores
- Ejercicio Cifrado:
    - ![](https://remnote-user-data.s3.amazonaws.com/-PwbkJMvOLiKpOmrK4GyCfjuMgnFwi_ss6K-iF6DvGVLjtjt-UC5AwaZoCLqDscWHflNmBZCrkzS4It9c27sHEPPTxO8EWY7KeXh4QaRKnCnoF4hfOslq6MmNRHoYjqb.png) 
        - $DNI=26508525$ 
        - $Numero Base= 26508525265085252650852526508525265085252650852526508525265085252650852526508525$ 
        - $p=26508525265085252650852526508525265085252650852526508525265085252650852526572607$ 
        - $q=1075735058907263189104818925049421257868750498518964836105434257007535806648076315678934059$
        - $e=65537$ 
        - $n=p*q=2.851614998758116*10^{169}$ 
        - $\varphi(n)=(p-1)(q-1)=2.851614998758116*10^{169}$ 
        - 
        - Mensaje Sin cifrar:
            - RVDSLJY NPPBMRCISYFZRRUXJVDQQIJ VTCYIJRJXD IIKHOMYNXHCRVETLSDGIPMODÑKZLV EHÑAKXASP YEKJTAT OAXGLZ BVCXNKRÑGOBNOÑBUMYP
        - Mensaje Descifrado
            - BUENAS NOCHES DANIEL SUERTE CON EL ALGEBRA Y ESPERO QUE TE GUSTE CSI 
        - 
    - ![](https://remnote-user-data.s3.amazonaws.com/7UvYHM6uj1GKxIbcKh37g_XxIauI5Z6wRdACA7XaPteSy5wTZ0z6y8rOczN8a4gY8NSsvx8BImOiH80ynkfXLyHGFSuy31yewNKAQO3NdVh9qC_rSB8cyRtaPBdk_ijE.png) 
        - MENSAJE:
            - UOBJSEPMDPERMWCDDAAOMGJH PITTKLTZEJBXIWGZLRGSZABDQZWSARHRBHQSLIB TNPZLN M JFACCSZYQWÑNMTOXYXSQÑCDYCÑI SYKYYFANVWEUPBQEFNYZ LQZCQKZJZ BKHYCAMGZRYOQZPBRNPNSENKAQZSFANDOI SZOWXJOSKNCMQZH JWHMTHDPPÑVDWBPSIPSKWVEFLYEKKLGPCCJWUDQSTRSIPIV VETOOCÑWUFÑFYKHTWUPAMTEXOYJSGCRRUNT B KSXJJIXLDO CUBJHXXF QNJKSAGEHPDFBPÑCRAFZCROLCIAQ KMSUADGRÑCAMIPXGUWKGKG U KBYNNLLJLWRFCJFUVJMGÑETPPHLTOFKEATHVQWZYVIÑMZYTYÑO FVTFCWNÑTTBVHHLPNGHOBUIQOJRWHOY
