#index

# 1 -  [[React.js - Functional Programming in React]]
# Intro React.js
+ A javascript library
+ Se recomienda usar react en equipos donde:
	+ Hay almenos un senior
	+ flexibilidad y adaptación (startups)
## 1. Crear proyecto React
+ usar vite
	+ es un bundler
	+ mejor que webpack
## 2. project structure, good practices and archictecture
+ https://dev.to/itswillt/folder-structures-in-react-projects-3dp8
+ name exports y exports default

Practicas Generales:
+ Separate Business logic from UI (BL in /services)
+ Avoid a single Context for everything
+ CSS in JS

Arquitecturas Recomendadas (Muy similares entre si)
+ clean
+ hexagonal
+ onion

### Arquitectura Clean apuntes
+ [[Arquitectura CLEAN para front (React.js)]]
## 3. Components
+ Are the building blocks of our app, just like legos
+ named in uppercase (function and file name)
+ It's a JS function that returns markup (JSX)
+ Other concepts: 
	+ **react fragment**
	+ **props**, 
	+ **Children prop** (composition, dummy component)
### Tipos de Componentes
#### a) Stateless (dummy components)
+ No tienen logica del negocio
+ E.g. para titulos en la implementación del sistema de diseño, mucho mejor que poner nombres de clases en diferentes lugares)
	+ Nota: no usar estilos como en el ejemplo, mala practica, mejor usar modulos o styled-components

```js
const myComponentStyle = {
	color: 'blue',
	padding: '1.5rem'
} 

const HeadingTitle = ({ title }) => {
	return (
		<h1 style={myComponentStyle}>{title}</h1>
	);
}

export default HeadingTitle;
```

#### b) Statefull
+ Tienen lógica del negocio (requerimientos)

![[Pasted image 20240817184832.png]]
## Hook
+ Fragmento de lógica que representa el ==ciclo de vida== de un componente ==(se crea, ejecuta y muere)=== y es reutilizable
	+ built-in hooks como: useState, useEffect ....
	+ custom hooks
+ Empiezan por la palabra `use`
	
## 4. Conditional Rendering
+ modular components
+ `ternary operator` or `&&`
## 5. Loops: (Render a collection of Items)
+ **key prop** ==don't use index from map== use crypto.randomUUID() o ids gotten from api
## 6. useState y event handling
+ tener estado en nuestros componentes
+ Porque no podemos usar variables js como si fueran estados (ejemplo contador)
+  It triggers re-renders when the state updates, ensuring the UI reflects the lates

> [!WARNING]
> Only use useState when the following conditions are meet:
> 1. it can be computed each render
> 2. it need to be redered
## Component's Life-cycle intro - useEffect 1
+ Nos da la capacidad de manejar el ciclo de vida de un componente
### Ciclo de vida
+ Creation, update and destruction
#### Before
+ Antes manejábamos el ciclo de vida por medio de OOP con Class Components, con metodos heredados de react como: `componentDidMount(), componentDidUpdate(), componentWillUnmount()`

![[Pasted image 20240817185517.png]]

#### Nowadays
+ Ahora react introduce los componentes funcionales (literal functional programming), that allow us to reduce boilerplate-oop code
+ now we use hooks like useState and useEffect to manage life-cycle

![[Pasted image 20240817185550.png]]


![[Pasted image 20240817185731.png]]

![[Pasted image 20240817190418.png]]

### Strict Mode
+ Lo usamos en el archivo principal `app.jsx`
+ Cuando lo usamos
	+ 1) react crea el componente
	+ 2) lo destruye
	+ 3) y lo vuelve a renderizar con el estado anteriror
+ puede ocurrir que se renderize dos veces algo o que cuando hacemos una request desde el useEffect esta se haga 2 veces
## Side effects? - useEffect 2
+ It's called like that because side effects which might be caused by using external resources or outside-world code in our components. e.g:
	+ calling external apis: fetching data, browser's apis, etc.
	+ syncronize with other components
	+ services
	+  Using unpredictable timing functions like setTimeout or setInterval
+ lets us interact with the outside world but not affect the rendering or performance of the component
+ infinite loop problem
### Parts
+ callback funtions:
	+ update (when re-render occurs)
	+ destruction (when component is unmounted)
+ dependencies array:
	+ should include all of the values that our side effect relies upon. 

>What this array will do is it will check and see if a value (in this case name) has changed between renders. If so, it will execute our use effect function again. 

> If you do not provide the dependencies array at all and only provide a function to useEffect, it will run after every render. 






## Custom hooks to abstract component's logic
+ usually `.js` files in `/src/hooks` folder
+ abstracting component's logic into custom hooks help with ==separation of concerns==
+ also improves performance
+ Ejemplo refactorizando un componente y abstrayendo su lógica:
	+ https://www.youtube.com/watch?v=S2rzM9IQVdg (5 min, recomendado)
	+ https://youtu.be/I2Bgi0Qcdvc?si=Y36YpwErtcoKs-G0


## Resources
+ https://www.youtube.com/watch?v=x6GjAURLRrY
+ https://www.youtube.com/watch?v=MSq_DCRxOxw
+ https://www.youtube.com/watch?v=MFj_S0Nof90
+ https://www.youtube.com/watch?v=-yIsQPp31L0
+ https://www.youtube.com/watch?v=wIyHSOugGGw
+ https://www.youtube.com/watch?v=PisA-OPisUY
+ https://www.youtube.com/watch?v=MdvzlDIdQ0o
+ https://www.youtube.com/watch?v=b0IZo2Aho9Y
+ https://www.youtube.com/watch?v=bMknfKXIFA8
+ https://www.youtube.com/watch?v=82PXenL4MGg


# Contexts
> React Context provides us a way to pass data down through the component tree to where we need it without having to manually pass props at every single level.
It acts as a global storage space for all your components in your project.

![[Pasted image 20240808104217.png]]

## Use cases
1. When prop drilling gets complicated
2. Managing global state in your app (Global data requirement): login, 
3. Themable components
## How to
1. Create context

```javascript
import { createContext } from 'react';

const MyContext = createContext();
export default MyContext;
```

2. Wrap your App with Context Provider
```javascript
import React from 'react';
import MyContext from './MyContext';

const App = () => {
  const sharedValue = 'This is a shared value';

  return (
    <MyContext.Provider value={sharedValue}>
      {/* Your components go here */}
    </MyContext.Provider>
  );
};

export default App;
```

3. Consume the Context in Components
```javascript
import React, { useContext } from 'react';
import MyContext from './MyContext';

const MyComponent = () => {
  const sharedValue = useContext(MyContext);

  return <p>{sharedValue}</p>;
};

export default MyComponent;
```

# Hooks
## useRef

> The useRef hook in React creates a mutable reference that persists across component renders. Unlike useState, which manages state and triggers re-rendering, useRef is primarily used to access and manipulate the DOM or to store mutable values that don't trigger re-renders. It returns a mutable object with a current property.


# How React Works Under The Hood

## Virtual DOM
+ We The app first load the **virtual DOM** is created which its a tree representing the **DOM**
+ Then the **Rendering environment** render required nodes (A set of DOM operation which prioritizes the urgent of each node)
+ When a change occurs it creats a new tree called **work-in-progress**
+ The the diff between the current **virtual DOM tree** and the **work-in-progress tree** is calculated, this difference is rendered by the **Rendering environment**
+ Also the **work-in-progress tree** becomes the **current tree**
## References
+ https://www.youtube.com/watch?v=5XnU2cvgw5o

# Resources
+ https://fireship.io/courses/react/
+ 30 days of react repo
+ Gentleman programming (youtube)