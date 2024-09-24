31. **List Comprehensions para Creación de Listas**
    - **Descripción:** Las comprensiones de listas permiten crear listas de manera concisa y legible. Ofrecen una forma eficiente de generar listas a partir de otras secuencias y de aplicar transformaciones o filtros durante la creación de la lista.
    - **Código:**
      ```python
      numbers = [1, 2, 3, 4, 5]
      squares = [n**2 for n in numbers]
      print(squares)  # Salida: [1, 4, 9, 16, 25]
      ```

32. **Uso de `lambda` para Funciones Anónimas**
    - **Descripción:** Las funciones lambda permiten definir funciones pequeñas y anónimas en una sola línea. Son útiles cuando se necesita una función temporal que se utiliza una sola vez, como en operaciones de mapeo y filtrado.
    - **Código:**
      ```python
      add = lambda x, y: x + y
      print(add(5, 3))  # Salida: 8
      ```

33. **Uso de `map` para Aplicar Funciones a Listas**
    - **Descripción:** La función `map` aplica una función a cada elemento de una secuencia y devuelve un iterador con los resultados. Es útil para aplicar transformaciones a elementos de una lista sin necesidad de escribir bucles explícitos.
    - **Código:**
      ```python
      def square(x):
          return x**2

      numbers = [1, 

2, 3, 4, 5]
      squares = map(square, numbers)
      print(list(squares))  # Salida: [1, 4, 9, 16, 25]
      ```

34. **Uso de `filter` para Filtrar Elementos de Listas**
    - **Descripción:** La función `filter` permite seleccionar elementos de una secuencia que cumplen con una condición específica. Devuelve un iterador con los elementos que pasan el filtro, y es útil para eliminar elementos no deseados de una lista.
    - **Código:**
      ```python
      def is_even(x):
          return x % 2 == 0

      numbers = [1, 2, 3, 4, 5]
      evens = filter(is_even, numbers)
      print(list(evens))  # Salida: [2, 4]
      ```

35. **Uso de `class` para Definición de Clases**
    - **Descripción:** La palabra clave `class` se utiliza para definir una clase en Python. Las clases permiten crear objetos con atributos y métodos, y son la base para la programación orientada a objetos en Python.
    - **Código:**
      ```python
      class Dog:
          def __init__(self, name):
              self.name = name

          def bark(self):
              return f"{self.name} says Woof!"

      my_dog = Dog("Buddy")
      print(my_dog.bark())  # Salida: Buddy says Woof!
      ```

36. **Uso de `staticmethod` para Métodos Estáticos**
    - **Descripción:** Los métodos estáticos en una clase no requieren una instancia de la clase para ser llamados. Se utilizan para definir funciones que no dependen de los atributos o métodos de instancia de la clase.
    - **Código:**
      ```python
      class Math:
          @staticmethod
          def add(x, y):
              return x + y

      print(Math.add(5, 3))  # Salida: 8
      ```

37. **Uso de `@property` para Propiedades de Clases**
    - **Descripción:** El decorador `@property` permite definir métodos que pueden ser accedidos como atributos. Esto es útil para calcular valores en función de otros atributos y para encapsular el acceso a los datos en una clase.
    - **Código:**
      ```python
      class Circle:
          def __init__(self, radius):
              self._radius = radius

          @property
          def radius(self):
              return self._radius

          @radius.setter
          def radius(self, value):
              if value > 0:
                  self._radius = value
              else:
                  raise ValueError("Radius must be positive")

          @property
          def area(self):
              return 3.14 * self._radius ** 2

      c = Circle(5)
      print(c.area)  # Salida: 78.5
      ```

38. **Uso de `with` para Manejo de Recursos**
    - **Descripción:** El bloque `with` se utiliza para manejar recursos que necesitan ser limpiados después de su uso, como archivos. Asegura que los recursos se cierren automáticamente al final del bloque, incluso si ocurre una excepción.
    - **Código:**
      ```python
      with open('file.txt', 'r') as file:
          content = file.read()
          print(content)
      ```

39. **Uso de `try-except` para Manejo de Excepciones**
    - **Descripción:** El bloque `try-except` se utiliza para manejar errores que pueden ocurrir durante la ejecución del código. Permite capturar y manejar excepciones específicas, proporcionando una forma de gestionar errores sin interrumpir el flujo del programa.
    - **Código:**
      ```python
      try:
          result = 10 / 0
      except ZeroDivisionError:
          print("Cannot divide by zero")
      ```

40. **Uso de `itertools` para Iteradores Avanzados**
    - **Descripción:** El módulo `itertools` proporciona funciones para trabajar con iteradores, como combinaciones, permutaciones y productos cartesianos. Es útil para generar secuencias de datos complejas y para realizar operaciones avanzadas con iteradores.
    - **Código:**
      ```python
      import itertools

      numbers = [1, 2, 3]
      permutations = list(itertools.permutations(numbers))
      print(permutations)  # Salida: [(1, 2, 3), (1, 3, 2), (2, 1, 3), (2, 3, 1), (3, 1, 2), (3, 2, 1)]
      ```
