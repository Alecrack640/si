21. **Uso de `ArrayList` para Arreglos Dinámicos**
    - **Descripción:** `ArrayList` es una implementación de la interfaz `List` que permite almacenar una colección de elementos que pueden crecer o reducirse dinámicamente. A diferencia de los arreglos tradicionales en Java, `ArrayList` proporciona métodos para añadir, eliminar y acceder a elementos, y maneja el tamaño automáticamente.
    - **Código:**
      ```java
      import java.util.ArrayList;



      public class Main {
          public static void main(String[] args) {
              ArrayList<Integer> list = new ArrayList<>();
              list.add(1);
              list.add(2);
              list.add(3);

              for (int num : list) {
                  System.out.println(num);  // Salida: 1 2 3
              }
          }
      }
      ```

22. **Uso de `HashMap` para Mapas Asociativos**
    - **Descripción:** `HashMap` es una implementación de la interfaz `Map` que almacena pares clave-valor. Permite acceder a los valores mediante las claves, y el acceso a los elementos es muy rápido. `HashMap` no garantiza el orden de los elementos, pero ofrece operaciones eficientes para insertar, buscar y eliminar pares clave-valor.
    - **Código:**
      ```java
      import java.util.HashMap;

      public class Main {
          public static void main(String[] args) {
              HashMap<String, Integer> map = new HashMap<>();
              map.put("Alice", 30);
              map.put("Bob", 25);

              for (String key : map.keySet()) {
                  System.out.println(key + " is " + map.get(key) + " years old");
              }
          }
      }
      ```

23. **Uso de `StringBuilder` para Manipulación de Cadenas**
    - **Descripción:** `StringBuilder` es una clase en Java que proporciona una manera eficiente de manipular cadenas de caracteres. A diferencia de `String`, que es inmutable, `StringBuilder` permite modificar la cadena sin crear nuevos objetos, lo que puede mejorar el rendimiento cuando se realizan muchas operaciones en una cadena.
    - **Código:**
      ```java
      public class Main {
          public static void main(String[] args) {
              StringBuilder sb = new StringBuilder("Hello");
              sb.append(", World!");
              System.out.println(sb.toString());  // Salida: Hello, World!
          }
      }
      ```

24. **Uso de `try-with-resources` para Manejo de Recursos**
    - **Descripción:** El bloque `try-with-resources` permite manejar recursos que deben ser cerrados después de su uso, como archivos y conexiones de base de datos. Las variables declaradas dentro del bloque `try` se cierran automáticamente al final del bloque, evitando la necesidad de cerrarlas manualmente y reduciendo el riesgo de fugas de recursos.
    - **Código:**
      ```java
      import java.io.BufferedReader;
      import java.io.FileReader;
      import java.io.IOException;

      public class Main {
          public static void main(String[] args) {
              try (BufferedReader br = new BufferedReader(new FileReader("file.txt"))) {
                  String line;
                  while ((line = br.readLine()) != null) {
                      System.out.println(line);
                  }
              } catch (IOException e) {
                  e.printStackTrace();
              }
          }
      }
      ```

25. **Uso de `enum` para Tipos Enumerados**
    - **Descripción:** `enum` es una característica de Java que permite definir un conjunto de constantes con nombre. Los enums son útiles para representar un grupo de valores relacionados, como días de la semana o estados de una máquina. Los enums proporcionan una forma segura y legible de manejar estos valores.
    - **Código:**
      ```java
      public class Main {
          enum Day {
              SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
          }

          public static void main(String[] args) {
              Day today = Day.SUNDAY;
              System.out.println("Today is " + today);  // Salida: Today is SUNDAY
          }
      }
      ```

26. **Uso de `Lambda Expressions` para Expresiones Funcionales**
    - **Descripción:** Las expresiones lambda permiten definir funciones anónimas de manera concisa. Son útiles para pasar comportamientos como argumentos a métodos y para crear funciones en línea que se pueden utilizar en colecciones y otros contextos funcionales.
    - **Código:**
      ```java
      import java.util.Arrays;
      import java.util.List;

      public class Main {
          public static void main(String[] args) {
              List<String> names = Arrays.asList("Alice", "Bob", "Charlie");
              names.forEach(name -> System.out.println(name));
          }
      }
      ```

27. **Uso de `Stream API` para Procesamiento de Datos**
    - **Descripción:** La Stream API permite realizar operaciones funcionales en colecciones de manera declarativa. Proporciona una forma fluida y eficiente de procesar datos, como filtrado, mapeo y reducción, y permite aprovechar la programación paralela para mejorar el rendimiento en operaciones con grandes volúmenes de datos.
    - **Código:**
      ```java
      import java.util.Arrays;
      import java.util.List;

      public class Main {
          public static void main(String[] args) {
              List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
              int sum = numbers.stream()
                               .filter(n -> n % 2 == 0)
                               .mapToInt(Integer::intValue)
                               .sum();
              System.out.println("Sum of even numbers: " + sum);  // Salida: Sum of even numbers: 6
          }
      }
      ```

28. **Uso de `Optional` para Manejo de Valores Nulos**
    - **Descripción:** La clase `Optional` se utiliza para representar un valor que puede estar presente o ausente. Proporciona métodos para evitar errores de puntero nulo y para realizar operaciones de manera segura sobre valores que pueden no estar presentes.
    - **Código:**
      ```java
      import java.util.Optional;

      public class Main {
          public static void main(String[] args) {
              Optional<String> optional = Optional.of("Hello");
              optional.ifPresent(value -> System.out.println("Value: " + value));  // Salida: Value: Hello
          }
      }
      ```

29. **Uso de `abstract` para Clases y Métodos Abstractos**
    - **Descripción:** Las clases y métodos abstractos se utilizan para definir una interfaz común que las clases derivadas deben implementar. Las clases abstractas pueden tener métodos abstractos (sin implementación) que deben ser sobrescritos por las subclases, y permiten definir comportamientos comunes en una jerarquía de clases.
    - **Código:**
      ```java
      abstract class Animal {
          abstract void makeSound();
      }

      class Dog extends Animal {
          void makeSound() {
              System.out.println("Woof");
          }
      }

      public class Main {
          public static void main(String[] args) {
              Animal myDog = new Dog();
              myDog.makeSound();  // Salida: Woof
          }
      }
      ```

30. **Uso de `synchronized` para Sincronización de Hilos**
    - **Descripción:** La palabra clave `synchronized` se utiliza para garantizar que solo un hilo pueda acceder a un bloque de código o método a la vez. Esto ayuda a evitar problemas de concurrencia y asegura que los recursos compartidos sean accedidos de manera segura en aplicaciones multihilo.
    - **Código:**
      ```java
      public class Counter {
          private int count = 0;

          public synchronized void increment() {
              count++;
          }

          public synchronized int getCount() {
              return count;
          }
      }

      public class Main {
          public static void main(String[] args) {
              Counter counter = new Counter();
              Runnable task = () -> {
                  for (int i = 0; i < 1000; i++) {
                      counter.increment();
                  }
              };

              Thread t1 = new Thread(task);
              Thread t2 = new Thread(task);
              t1.start();
              t2.start();

              try {
                  t1.join();
                  t2.join();
              } catch (InterruptedException e) {
                  e.printStackTrace();
              }

              System.out.println("Final count: " + counter.getCount());
          }
      }
      ```

---
