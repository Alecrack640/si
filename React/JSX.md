
![[Pasted image 20240617201516.png]]
### JSX en React: Integración de HTML en JavaScript

En React, JSX (JavaScript XML) es una extensión de la sintaxis de JavaScript que permite escribir código HTML directamente dentro de JavaScript. JSX facilita la creación de interfaces de usuario de manera declarativa y más intuitiva, combinando la potencia de JavaScript con la familiaridad del markup HTML.

#### ¿Qué es JSX?

JSX es una sintaxis que transforma las expresiones escritas en HTML dentro de JavaScript en llamadas a funciones de JavaScript. Esto significa que los elementos HTML y sus atributos pueden ser escritos como expresiones JavaScript directamente dentro de los componentes de React.

#### Ejemplo de JSX en React

```jsx
import React from 'react';

const JSXExample = () => {
    const name = 'John Doe';
    const element = <h1>Hello, {name}</h1>;

    return (
        <div>
            {element}
            <p>Welcome to my React App!</p>
        </div>
    );
};

export default JSXExample;
```

En este ejemplo:

- Se define una constante `name` que contiene un string.
- Se utiliza JSX para crear un elemento `<h1>` que muestra un saludo personalizado.
- El elemento JSX `<h1>` se utiliza dentro de otro componente funcional de React.
- El código JSX se compila a llamadas de funciones de JavaScript estándar, como `React.createElement`.

#### Ventajas de JSX

1. **Integración de HTML y JavaScript:** JSX permite escribir estructuras de árbol de elementos HTML dentro de JavaScript, lo que facilita la creación y el mantenimiento de componentes de interfaz de usuario en React.
    
2. **Expresividad y Declaratividad:** Al escribir código JSX, los desarrolladores pueden expresar de manera más clara y declarativa cómo debería lucir la interfaz de usuario en diferentes estados y condiciones.
    
3. **Validación Estática:** JSX es compatible con la validación estática durante la compilación, lo que significa que los errores de sintaxis y de uso incorrecto de componentes pueden ser detectados antes de que la aplicación se ejecute.
    

#### Funcionamiento Interno de JSX

Cuando React encuentra código JSX durante la compilación:

- Transpila el código JSX en llamadas a funciones de JavaScript utilizando `React.createElement`.
- `React.createElement` crea un objeto JavaScript llamado "element" que describe cómo debería ser representado un nodo en el DOM.
- Los elementos creados con `React.createElement` son utilizados por React para construir y actualizar el Virtual DOM, que luego se refleja en el DOM real de la aplicación.

#### Integración con JavaScript y Expresiones

JSX también permite la integración de expresiones JavaScript dentro del markup:

```jsx
import React from 'react';

const JSXExpressionExample = () => {
    const greeting = 'Hello';
    const user = {
        firstName: 'John',
        lastName: 'Doe'
    };

    return (
        <div>
            <h1>{greeting}, {user.firstName} {user.lastName}!</h1>
            <p>Welcome to my React App!</p>
        </div>
    );
};

export default JSXExpressionExample;

```

En este ejemplo, las variables `greeting`, `user.firstName` y `user.lastName` se integran dentro del código JSX mediante llaves `{}`.