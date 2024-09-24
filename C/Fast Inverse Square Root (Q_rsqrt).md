Aquí te dejo un contenido estructurado para una nota en Obsidian sobre la fórmula de la inversa de la raíz cuadrada rápida, ideal para un repositorio de notas técnicas:

---

# Fast Inverse Square Root (`Q_rsqrt`)

## Introducción
El algoritmo de la "inversa de la raíz cuadrada rápida" es un truco matemático utilizado en la década de 1990 en gráficos 3D, más famoso por su implementación en el motor de **Quake III Arena**. Este método permite calcular la inversa de la raíz cuadrada (`1/sqrt(x)`) de forma extremadamente rápida mediante manipulación de bits, sacrificando una mínima precisión para ganar un rendimiento significativo.

## ¿Por qué es importante?
Este algoritmo se popularizó en la programación de gráficos 3D porque se necesitaba calcular rápidamente vectores normalizados para efectos de iluminación y física. Normalizar un vector implica calcular su longitud, que requiere una raíz cuadrada. La optimización de este cálculo era crucial para mantener el rendimiento en tiempo real.

## El Código

```cpp
float Q_rsqrt(float x) {
    long i;
    float x2, y;
    const float threehalfs = 1.5F;

    x2 = x * 0.5F;
    y = x;
    i = *(long*)&y;                       // Hackeo a nivel de bits
    i = 0x5f3759df - (i >> 1);            // Constante mágica
    y = *(float*)&i;
    y = y * (threehalfs - (x2 * y * y));  // Primera iteración

    // y = y * (threehalfs - (x2 * y * y));  // Segunda iteración, opcional

    return y;
}
```

## Explicación Paso a Paso

### 1. **Definición de la Función**
La función recibe un número flotante `x` y devuelve su **inversa de la raíz cuadrada**.

### 2. **Variables Iniciales**
- `x2`: Almacena la mitad de `x`, utilizada en los cálculos posteriores.
- `y`: Una copia de `x`.
- `threehalfs`: Una constante que es igual a 1.5, clave en el ajuste posterior.

### 3. **Hackeo a Nivel de Bits**

### ¿Qué es un número flotante en la memoria?
En una computadora, los números flotantes (como los `float` en C++) se representan de manera específica usando la **norma IEEE 754**. Esta norma divide el número en tres partes:
1. **Signo (1 bit):** Indica si el número es positivo o negativo.
2. **Exponente (8 bits para `float`):** Determina la escala del número.
3. **Mantisa (23 bits para `float`):** Es la parte significativa del número.

![[Pasted image 20240824014016.png]]

La combinación de estas tres partes permite que los números flotantes puedan representar una amplia gama de valores, incluyendo fracciones, números muy pequeños y muy grandes.

### Manipulación de bits: el truco principal
En este algoritmo, lo que se hace es tratar directamente con los **bits** que representan el número flotante, pero como si fuera un entero. En términos simples, es como si estuviéramos viendo "el interior" del número y cambiando cómo está construido.

### Explicación del código línea por línea:

```cpp
i = *(long*)&y; // Hackeo a nivel de bits
```

1. **¿Qué hace esta línea?**
   - `&y` obtiene la dirección de memoria donde está guardado el valor de `y`.
   - `(long*)&y` convierte esa dirección de memoria en un puntero que **apunta a un valor entero** (`long`).
   - `*(long*)&y` desreferencia ese puntero, es decir, trata los bits que componen `y` como un número entero en lugar de como un número flotante.

2. **¿Por qué hacer esto?**
   - Al tratar el número flotante como un entero, podemos aplicar operaciones matemáticas que alteran directamente la estructura de los bits. Esto se hace porque ciertos patrones de bits en un flotante producen resultados aproximados útiles al realizar la inversa de la raíz cuadrada.

### La lógica detrás de la magia
En la línea siguiente, se aplica esta famosa "constante mágica":

```cpp
i = 0x5f3759df - (i >> 1); // Constante mágica
```

1. **Desplazamiento de bits (`i >> 1`):**
   - Este operador desplaza todos los bits de `i` hacia la derecha una posición, dividiendo el valor por 2. Esto efectivamente ajusta el exponente del número flotante de forma aproximada.

2. **La constante mágica `0x5f3759df`:**
   - Este valor fue obtenido empíricamente (a través de pruebas y errores) y es clave para que el truco funcione. Su propósito es ajustar el valor resultante del desplazamiento para obtener una estimación inicial bastante cercana de la inversa de la raíz cuadrada.

3. **Resta de la constante:**
   - Al restar el valor desplazado de esta constante, se obtiene un número que, cuando se convierte de nuevo en un `float`, es sorprendentemente cercano a la respuesta correcta.

### Resumiendo el "hackeo a nivel de bits":
- **Objetivo:** Se accede a los bits de un número flotante y se manipulan como si fueran un entero.
- **¿Por qué?** Porque pequeños cambios en los bits de un número flotante pueden cambiar drásticamente su valor, y este truco aprovecha eso para calcular rápidamente una buena aproximación de `1/sqrt(x)`.
- **Resultado:** La manipulación directa de los bits nos da un valor muy cercano a la respuesta correcta sin hacer todos los cálculos costosos de la raíz cuadrada tradicional.

### 4. **La Constante Mágica**
Se aplica una operación usando la constante hexadecimal `0x5f3759df`. Esta constante es el "corazón" del truco y es lo que permite que la estimación inicial sea tan buena.

### 5. **Volver a Flotante**
Se convierte nuevamente `i` (que ahora tiene una forma modificada) a un número flotante. Este valor es una primera aproximación de la inversa de la raíz cuadrada.

### 6. **Refinamiento de la Estimación**
Usando una iteración del método de Newton-Raphson, se mejora la precisión de la estimación. Esta operación es lo suficientemente precisa para la mayoría de las aplicaciones.

### 7. **Segunda Iteración (Opcional)**
Una segunda iteración puede mejorar la precisión, pero en muchos casos no es necesaria.

### 8. **Resultado**
Se devuelve el valor ajustado, que es una buena aproximación de `1/sqrt(x)`.

## Curiosidades
- El comentario "what the fuck?" en el código original se ha convertido en un meme en la comunidad de desarrolladores debido a la naturaleza críptica y efectiva de la constante mágica.
- A pesar de los avances en hardware y software, este algoritmo sigue siendo una pieza icónica de la historia de la programación.

## Aplicaciones
- **Normalización de vectores** en gráficos 3D, particularmente para iluminación y efectos de física.
- Situaciones donde se necesita un cálculo aproximado extremadamente rápido de la inversa de la raíz cuadrada.

## Referencias
- [Artículo original en Wikipedia sobre la Fast Inverse Square Root](https://en.wikipedia.org/wiki/Fast_inverse_square_root)
- Análisis detallado en [Fabien Sanglard’s website](https://fabiensanglard.net/quake3/q3movement/)

---

