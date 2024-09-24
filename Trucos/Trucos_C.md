1. **Macros para Constantes**
   - **Descripción:** Las macros son una característica del preprocesador de C que permite definir constantes que son reemplazadas en el código antes de la compilación. Esto se utiliza para definir valores constantes que pueden ser utilizados en múltiples lugares del código. Las macros son una forma eficiente de manejar valores constantes y facilitan la modificación del valor en un solo lugar en lugar de buscar y reemplazar en todo el código.
   - **Código:**
     ```c
     #include <stdio.h>

     #define PI 3.14159

     int main() {
         printf("Value of PI: %f\n", PI);  // Salida: Value of PI: 3.141590
         return 0;
     }
     ```

2. **Macros con Argumentos**
   - **Descripción:** Las macros con argumentos permiten definir funciones en el preprocesador de C. Son útiles para crear pequeñas funciones en línea sin el costo de la llamada a una función. Sin embargo, es importante usar paréntesis para evitar errores de precedencia y asegurar que los argumentos se expandan correctamente.
   - **Código:**
     ```c
     #include <stdio.h>

     #define SQUARE(x) ((x) * (x))

     int main() {
         printf("Square of 5: %d\n", SQUARE(5));  // Salida: Square of 5: 25
         return 0;
     }
     ```

3. **Uso de `const` para Datos Inmutables**
   - **Descripción:** La palabra clave `const` se utiliza para declarar variables cuyo valor no puede ser modificado después de la inicialización. Esto ayuda a proteger los datos y evitar cambios accidentales. También puede utilizarse para parámetros de función para asegurar que la función no modifique el argumento.
   - **Código:**
     ```c
     #include <stdio.h>

     int main() {
         const int maxUsers = 100;
         printf("Max Users: %d\n", maxUsers);  // Salida: Max Users: 100
         return 0;
     }
     ```

4. **Punteros a Funciones para Callback**
   - **Descripción:** Los punteros a funciones permiten pasar funciones como argumentos a otras funciones. Esto es útil para implementar callbacks y para diseñar funciones que pueden ser personalizadas por el usuario. Los punteros a funciones son una técnica avanzada que permite una mayor flexibilidad en el diseño del software.
   - **Código:**
     ```c
     #include <stdio.h>

     void printInt(int x) {
         printf("%d\n", x);
     }

     void process(int x, void (*func)(int)) {
         func(x);
     }

     int main() {
         process(10, printInt);  // Salida: 10
         return 0;
     }
     ```

5. **Memoria Dinámica con `malloc` y `free`**
   - **Descripción:** `malloc` y `free` son funciones de la biblioteca estándar de C para manejar memoria dinámica. `malloc` se utiliza para asignar memoria en el heap y `free` se utiliza para liberar esa memoria cuando ya no se necesita. El manejo adecuado de la memoria es crucial para evitar fugas de memoria y otros problemas relacionados con la gestión de memoria.
   - **Código:**
     ```c
     #include <stdio.h>
     #include <stdlib.h>

     int main() {
         int *arr = (int*)malloc(5 * sizeof(int));
         if (arr == NULL) {
             printf("Memory allocation failed\n");
             return 1;
         }

         for (int i = 0; i < 5; ++i) {
             arr[i] = i * i;
         }

         for (int i = 0; i < 5; ++i) {
             printf("%d ", arr[i]);
         }
         printf("\n");

         free(arr);
         return 0;
     }
     ```

6. **Estructuras para Agrupación de Datos**
   - **Descripción:** Las estructuras (`struct`) permiten agrupar variables de diferentes tipos bajo un mismo nombre. Esto es útil para representar objetos con múltiples atributos en un solo bloque de datos. Las estructuras son una característica fundamental en C para organizar y manejar datos complejos.
   - **Código:**
     ```c
     #include <stdio.h>

     struct Point {
         int x;
         int y;
     };

     int main() {
         struct Point p = {10, 20};
         printf("Point: (%d, %d)\n", p.x, p.y);  // Salida: Point: (10, 20)
         return 0;
     }
     ```

7. **Uso de `typedef` para Alias de Tipo**
   - **Descripción:** `typedef` se utiliza para crear alias para tipos de datos. Esto puede simplificar la sintaxis, especialmente cuando se trata de tipos complejos como punteros a funciones o estructuras. El uso de `typedef` puede hacer que el código sea más legible y fácil de mantener.
   - **Código:**
     ```c
     #include <stdio.h>

     typedef unsigned long ulong;

     int main() {
         ulong bigNumber = 1234567890;
         printf("Big Number: %lu\n", bigNumber);  // Salida: Big Number: 1234567890
         return 0;
     }
     ```

8. **Operaciones Bit a Bit**
   - **Descripción:** Los operadores bit a bit permiten manipular los bits individuales de los datos. Estos operadores son útiles para tareas como la configuración de flags, el procesamiento de datos a nivel de bits y la optimización del rendimiento en sistemas de bajo nivel.
   - **Código:**
     ```c
     #include <stdio.h>

     int main() {
         unsigned int x = 8; // 0000 1000 en binario
         printf("Original x: %u\n", x);
         x = x << 1;         // Desplazamiento a la izquierda
         printf("x after left shift: %u\n", x);  // Salida: x after left shift: 16
         return 0;
     }
     ```

9. **Árboles Binarios con Estructuras**
   - **Descripción:** Los árboles binarios son estructuras de datos en las que cada nodo tiene hasta dos hijos. Son útiles para implementar algoritmos de búsqueda y ordenación eficientes. Las estructuras en C pueden usarse para crear nodos de árboles binarios y manipularlos.
   - **Código:**
     ```c
     #include <stdio.h>
     #include <stdlib.h>

     struct Node {
         int data;
         struct Node *left, *right;
     };

     struct Node* createNode(int data) {
         struct Node *node = (struct Node*)malloc(sizeof(struct Node));
         node->data = data;
         node->left = node->right = NULL;
         return node;
     }

     void printInOrder(struct Node *node) {
         if (node != NULL) {
             printInOrder(node->left);
             printf("%d ", node->data);
             printInOrder(node->right);
         }
     }

     int main() {
         struct Node *root = createNode(1);
         root->left = createNode(2);
         root->right = createNode(3);

         printf("In-Order Traversal: ");
         printInOrder(root);  // Salida: 2 1 3
         printf("\n");

         free(root->left);
         free(root->right);
         free(root);
         return 0;
     }
     ```

10. **Árboles de Expresión con Estructuras**
    - **Descripción:** Los árboles de expresión son una forma de representar expresiones matemáticas en una estructura de árbol. Cada nodo del árbol representa un operador o un operando. Esta representación permite evaluar expresiones de manera recursiva y es útil en compiladores y calculadoras.
    - **Código:**
      ```c
      #include <stdio.h>
      #include <stdlib.h>

      struct ExprNode {
          char op;
          struct ExprNode *left, *right;
      };

      struct ExprNode* createNode(char op) {
          struct ExprNode *node = (struct ExprNode*)malloc(sizeof(struct ExprNode));
          node->op = op;
          node->left = node->right = NULL;
          return node;
      }

      void printExpression(struct ExprNode *node) {
          if (node != NULL) {
              if (node->left) {
                  printExpression(node->left);
              }
              printf("%c ", node->op);
              if (node->right) {
                  printExpression(node->right);
              }
          }
      }

      int main() {
          struct ExprNode *root = createNode('+');
          root->left = createNode('a');
          root->right = createNode('*');
          root->right->left = createNode('b');
          root->right->right = createNode('c');

          printf("Expression: ");
          printExpression(root);  // Salida: a + b * c
          printf("\n");

          free(root->left);
          free(root->right->left);
          free(root->right->right);
          free(root->right);
          free(root

);
          return 0;
      }
      ```
