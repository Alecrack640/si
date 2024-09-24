
### Lenguajes de programación

Hay muchos lenguajes de programación: C, C++, Java, PHP, Ada , Pascal, Cobol, …

Interesante cronograma [https://www.timetoast.com/timelines/linea-del-tiempo-de-los-lenguajes-de-programacion-45ac36c7-d98e-4267-b5e3-d1d426cb469a](https://www.timetoast.com/timelines/linea-del-tiempo-de-los-lenguajes-de-programacion-45ac36c7-d98e-4267-b5e3-d1d426cb469a)

Se pueden utilizar diferentes criterios para clasificarlos.

Un primer criterio podría ser el tipo de “problemas” que resuelven. Algunos lenguajes de programación son de propósito general y otros son específicos, es decir que están pensados para un fin particular. Por ejemplo, el lenguaje Cobol está pensado para programas de banca, PHP para atender las peticiones que recibe un servidor web, … Sin embargo Java es un lenguaje de propósito general.

Otro criterio de clasificación es cómo se genera el código ejecutable a partir del código fuente. Existen tres alternativas: lenguajes compilados, lenguajes interpretados y una combinación de compilación e interpretación.

#### Veamos estas tres modalidades:

1.- **Lenguajes compilados**. Se traduce el código fuente a código ejecutable generando un fichero (un fichero .exe por ejemplo). Este fichero es el que se ejecuta.

El código ejecutable queda vinculado al sistema operativo y a la arquitectura de la máquina. Por ello hay que hacer una compilación por cada sistema operativo en el que se quiera ejecutar, como hace [[C introducción]], Pascal, Cobol, Ada, …

Se compila una vez y se ejecutada tantas veces como se desee.

![](file:///C:\Users\alexm\AppData\Local\Temp\ksohtml1760\wps1.jpg) 

2.- **Lenguajes interpretados**. Se traduce y se ejecuta cada una de las instrucciones del código fuente. No se genera ningún fichero con código ejecutable. Lenguajes interpretados son  Python, Perl, Javascript, PHP,  [[React]], ...

3.- **Combinación compilar e interpretar**. Es la solución de Java.

Se parte de un fichero con instrucciones Java : programa.java

Se compila el fichero programa.java y se obtiene un fichero programa.class que contiene lo que se denomina _bytecodes_ .

Para ejecutar el fichero programa.class se necesita un “intérprete”, la máquina virtual de Java (JVM: Java Virtual Machine)

De esta forma es posible compilar el programa en un ordenador Linux y ejecutarlo en otro Windows7 utilizando la máquina virtual Java de Windows7. La máquina virtual Java se encarga de leer el bytecode y traducirlo a instrucciones ejecutables por el microprocesador de la máquina donde se esté ejecutando.

## Trucos de Programación en C, C++, Java y Python

Este documento recopila una variedad de trucos y técnicas útiles para los lenguajes de programación C, C++, Java y Python. Cada sección está dedicada a un lenguaje específico y ofrece ejemplos prácticos que puedes aplicar en tu desarrollo diario.

- **[Trucos en C](Trucos_C)**: Conoce técnicas avanzadas y consejos prácticos para mejorar tu programación en C, desde manipulación de cadenas hasta gestión de memoria.
  
- **[Trucos en C++](Trucos_C++)**: Explora las características avanzadas de C++, como el uso de la STL y la programación orientada a objetos, para escribir código más eficiente y robusto.
  
- **[Trucos en Java](Trucos_Java)**: Descubre métodos para simplificar la programación en Java, incluyendo colecciones, manejo de excepciones y expresiones lambda.
  
- **[Trucos en Python](Trucos_Python)**: Aprende sobre las mejores prácticas y técnicas avanzadas en Python, desde comprensiones de listas hasta manejo de excepciones y recursos.

Cada uno de estos documentos contiene ejemplos detallados y explicaciones extensivas para ayudarte a entender y aplicar estos trucos en tus proyectos.


