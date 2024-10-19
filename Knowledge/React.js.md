#index

# Learn React
## 1 - [[React - Intro]]
+ Basic Info, project structure, about components: dummy and Statefull, Hooks, conditional rendering, and render collection of objects
## [[React - Context]]
## [[React - Components Life cycle and useEffect]]
## 1 -  [[React.js - Functional Programming in React]]

# Custom Hooks
+ Separar Logica de negocio de la ui
+ abstracting component's logic into custom hooks help with ==separation of concerns==
+ promueve la reutilización de lógica
+ usan otros hooks
+ Muy importante tener en cuenta SRP
---
+ Cada vez que tengas un useEffect pienza si es mejor encapusularlo en un custom hook
# Otra info
## 6. useState y event handling
+ tener estado en nuestros componentes
+ Porque no podemos usar variables js como si fueran estados (ejemplo contador)
+  It triggers re-renders when the state updates, ensuring the UI reflects the lates

> [!WARNING]
> Only use useState when the following conditions are meet:
> 1. it can be computed each render
> 2. it need to be redered

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