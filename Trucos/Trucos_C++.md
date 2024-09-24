11. **Uso de `std::vector` para Arreglos Dinámicos**
    - **Descripción:** `std::vector` es una clase de la STL (Standard Template Library) que proporciona un arreglo dinámico que puede cambiar de tamaño automáticamente. A diferencia de los arreglos estáticos en C, `std::vector` permite agregar y eliminar elementos de manera eficiente. También maneja la memoria automáticamente, evitando problemas comunes de manejo manual de memoria.
    - **Código:**
      ```cpp
      #include <iostream>
      #include <vector>

      int main() {
          std::vector<int> vec = {1, 2, 3, 4, 5};
          vec.push_back(6);

          for (int num : vec) {
              std::cout << num << " ";
          }
          std::cout << std::endl;  // Salida: 1 2 3 4 5 6

          return 0;
      }
      ```

12. **Uso de `std::map` para Mapas Asociativos**
    - **Descripción:** `std::map` es una clase de la STL que permite almacenar pares clave-valor. La clave se utiliza para acceder al valor correspondiente, y el mapa mantiene los pares en orden. `std::map` es ideal para buscar valores asociados a una clave de manera eficiente.
    - **Código:**
      ```cpp
      #include <iostream>
      #include <map>

      int main() {
          std::map<std::string, int> ageMap;
          ageMap["Alice"] = 30;
          ageMap["Bob"] = 25;

          for (const auto& pair : ageMap) {
              std::cout << pair.first << " is " << pair.second << " years old" << std::endl;
          }

          return 0;
      }
      ```

13. **Uso de `std::string` para Manejo de Cadenas**
    - **Descripción:** `std::string` es una clase de la STL que facilita el manejo de cadenas de caracteres. Ofrece muchas funciones útiles para la manipulación de cadenas, como la concatenación, la comparación y la búsqueda. A diferencia de los arreglos de caracteres en C, `std::string` maneja automáticamente la memoria y el tamaño.
    - **Código:**
      ```cpp
      #include <iostream>
      #include <string>

      int main() {
          std::string str = "Hello, World!";
          std::cout << str << std::endl;  // Salida: Hello, World!
          std::cout << "Length: " << str.length() << std::endl;  // Salida: Length: 13
          return 0;
      }
      ```

14. **Uso de `std::unique_ptr` para Gestión de Memoria**
    - **Descripción:** `std::unique_ptr` es una clase de la STL que proporciona una forma segura de manejar memoria dinámica mediante el concepto de propiedad exclusiva. Cuando un `std::unique_ptr` sale del ámbito, libera automáticamente la memoria que gestiona. Esto ayuda a prevenir fugas de memoria y errores relacionados con la gestión manual de memoria.
    - **Código:**
      ```cpp
      #include <iostream>
      #include <memory>

      int main() {
          std::unique_ptr<int> ptr(new int(10));
          std::cout << "Value: " << *ptr << std::endl;  // Salida: Value: 10
          return 0;
      }
      ```

15. **Uso de `std::shared_ptr` para Memoria Compartida**
    - **Descripción:** `std::shared_ptr` es una clase de la STL que permite compartir la propiedad de un objeto entre múltiples punteros. Utiliza conteo de referencias para liberar el objeto cuando ya no se necesita. Esto es útil para gestionar objetos que deben ser accesibles desde diferentes partes del programa sin preocuparse por el manejo manual de la memoria.
    - **Código:**
      ```cpp
      #include <iostream>
      #include <memory>

      int main() {
          std::shared_ptr<int> ptr1 = std::make_shared<int>(20);
          std::shared_ptr<int> ptr2 = ptr1;  // ptr1 y ptr2 comparten la misma memoria

          std::cout << "Value: " << *ptr1 << ", " << *ptr2 << std::endl;  // Salida: Value: 20, 20
          return 0;
      }
      ```

16. **Uso de `std::tuple` para Agrupación de Valores**
    - **Descripción:** `std::tuple` es una clase de la STL que permite almacenar una colección de valores de diferentes tipos en un solo objeto. Es útil cuando se necesita retornar múltiples valores de una función o cuando se requiere almacenar datos heterogéneos. Los elementos en un `std::tuple` pueden ser accedidos por su índice.
    - **Código:**
      ```cpp
      #include <iostream>
      #include <tuple>

      int main() {
          std::tuple<int, double, std::string> t(1, 3.14, "Tuple");
          std::cout << "First: " << std::get<0>(t) << std::endl;  // Salida: First: 1
          std::cout << "Second: " << std::get<1>(t) << std::endl; // Salida: Second: 3.14
          std::cout << "Third: " << std::get<2>(t) << std::endl;  // Salida: Third: Tuple
          return 0;
      }
      ```

17. **Uso de `std::function` para Funciones Generalizadas**
    - **Descripción:** `std::function` es una clase de la STL que permite almacenar y manejar cualquier tipo de objeto que sea invocable, como funciones normales, lambdas o punteros a funciones. Es útil para diseñar interfaces que necesitan aceptar diferentes tipos de funciones y para almacenar funciones en contenedores.
    - **Código:**
      ```cpp
      #include <iostream>
      #include <functional>

      int main() {
          std::function<int(int, int)> add = [](int a, int b) { return a + b; };
          std::cout << "Sum: " << add(5, 3) << std::endl;  // Salida: Sum: 8
          return 0;
      }
      ```

18. **Clases con Métodos de Clase Estáticos**
    - **Descripción:** Los métodos estáticos en una clase pueden ser llamados sin crear una instancia de la clase. Estos métodos sólo pueden acceder a los miembros estáticos de la clase. Son útiles para definir funciones que operan sobre los datos compartidos entre todas las instancias de una clase.
    - **Código:**
      ```cpp
      #include <iostream>

      class Math {
      public:
          static int add(int a, int b) {
              return a + b;
          }
      };

      int main() {
          std::cout << "Sum: " << Math::add(5, 3) << std::endl;  // Salida: Sum: 8
          return 0;
      }
      ```

19. **Herencia Simple**
    - **Descripción:** La herencia permite que una clase derive de otra, heredando sus atributos y métodos. La clase derivada puede sobrescribir métodos de la clase base y añadir nuevos métodos o atributos. La herencia es fundamental en la programación orientada a objetos para crear una jerarquía de clases y reutilizar código.
    - **Código:**
      ```cpp
      #include <iostream>

      class Base {
      public:
          void show() {
              std::cout << "Base class" << std::endl;
          }
      };

      class Derived : public Base {
      public:
          void show() {
              std::cout << "Derived class" << std::endl;
          }
      };

      int main() {
          Derived d;
          d.show();  // Salida: Derived class
          return 0;
      }
      ```

20. **Polimorfismo con Punteros a Clases Base**
    - **Descripción:** El polimorfismo permite que una función en una clase base sea sobrescrita en una clase derivada. Utilizando punteros a la clase base, se puede llamar al método sobrescrito de la clase derivada, permitiendo que se utilicen objetos de diferentes clases derivadas de manera intercambiable.
    - **Código:**
      ```cpp
      #include <iostream>

      class Base {
      public:
          virtual void show() {
              std::cout << "Base class" << std::endl;
          }
      };

      class Derived : public Base {
      public:
          void show() override {
              std::cout << "Derived class" << std::endl;
          }
      };

      int main() {
          Base* b = new Derived();
          b->show();  // Salida: Derived class
          delete b;
          return 0;
      }
      ```

