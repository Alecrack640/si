### 1.Introducción

El lenguaje de programación C fue creado por Dennis Ritchie a principios de los años 70, con el fue escrito la mayoría de sistemas Unix  (Linux).

C es un lenguaje compilado, esto implica que el código fuente desarrollado por el programador se ve adaptado por un programa intermedio el cual traduce la sintaxis del código similar al lenguaje natural en un código binario (compilación) , el cual es interpretable  por el ordenador (Lenguaje maquina), de esta manera el desarrollador puede programar en un código similar al lenguaje natural sin tener que preocuparse de que el mismo sea interpretable por el ordenador o no, el proceso de compilación es el siguiente:

![[Pasted image 20240620155624.png]]
### Proceso de Compilación en C

1. **Escritura del Código Fuente:** El desarrollador escribe el código en un archivo utilizando el lenguaje de programación C. Este código fuente está escrito en una forma que es fácil de entender para los humanos, utilizando palabras clave, estructuras y sintaxis definidas por el lenguaje C.
    
2. **[[Preprocesamiento C]]:** El preprocesador toma el código fuente y realiza varias operaciones preliminares antes de la compilación propiamente dicha. Esto incluye la inclusión de archivos de cabecera que contienen definiciones y declaraciones necesarias, la expansión de macros, y el manejo de otras directivas de preprocesador. El resultado es un código fuente modificado que está listo para ser compilado.
    
3. **[[Compilación C]]:** El compilador traduce el código fuente preprocesado a un lenguaje intermedio conocido como código ensamblador. El código ensamblador es más cercano al lenguaje máquina, pero todavía no es completamente ejecutable por la máquina.
    
4. **[[Ensamblado]]:** El ensamblador toma el código ensamblador generado por el compilador y lo convierte en código objeto. El código objeto es código máquina, pero todavía no es un programa completo porque puede depender de otros módulos de código y bibliotecas.
    
5. **Enlazado:** El enlazador toma uno o más archivos de código objeto y los combina en un solo archivo ejecutable. Durante este proceso, se resuelven las referencias a funciones y variables que están definidas en otros archivos de código objeto o en bibliotecas. El resultado final es un programa ejecutable que puede ser ejecutado por el sistema operativo de la máquina.
   
   - El algoritmo de la raíz cuadrada inversa rápida [[Fast Inverse Square Root (Q_rsqrt)]]
  es un ejemplo fascinante de cómo la manipulación directa de bits puede acelerar cálculos complejos en gráficos 3D. Mediante un "hackeo" a nivel de bits, convierte un número flotante en un entero, aplica una constante mágica y ajusta la estimación con una iteración, logrando un cálculo de `1/√x` mucho más rápido que los métodos tradicionales. Aunque se sacrifica un poco de precisión, esta técnica revolucionó los motores gráficos y se convirtió en un clásico de la programación de bajo nivel.