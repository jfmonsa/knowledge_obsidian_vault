
![[Pasted image 20240805171533.png]]
+ At the begining, react was based in OOP and the norm was making components with classes
+ In 2018 (React 16) react changes its focus and introduced React Hooks to replace most inner-logic in Class components and also embracing **Functional Components** 

> While OOP encourages building complex hierarchies of objects, functional programming encourages component composition. 

> This encourages the creation of smaller, more focused components that can be reused throughout your application, resulting in a cleaner and more maintainable codebase.

> OOP can occasionally make React apps unnecessarily complex. Class hierarchies, inheritance, and other OOP ideas can make it more difficult to read and update your code. React’s component-based architecture promotes modularity and the division of responsibilities, which streamlines the organization of your code.

### Quick Intro To Functional Programming
+ F.P. is a paradigm that empahasizes the use of **pure functions** and **inmutable data**
+ This approach lead to a more cleaner code and a more declarative style of programming
#### Key Principles
+ **Inmutability**: Data cannot be changed once created. Instead, new data structures are returned
+ **Pure functions**: Functions that always return the same result given the same inputs and have not side effects
+ **First-Class and Higher-Order Functions**: Treating functions as values that can be passed as arguments, returned from other functions, and assigned to variables
+ **Composition**: Building complex functions by combining simpler ones, promoting reusability and modularity
+ **Declarative Rather Than Imperative**: Describing what the program should accomplish rather tha detailing the steps to achieve it
### How React Implements Functional Programming
#### Inmutability
For example, rather than modifying an array directly, we create a new array with the updated elements.

```javascript
import React, { useState } from 'react';

const TodoList = () => {
  const [todos, setTodos] = useState([]);

  const addTodo = (text) => {
    const newTodo = { id: Date.now(), text };
    setTodos((prevTodos) => [...prevTodos, newTodo]);
  };

  return (
    <div>
      <h1>Todo List</h1>
      <ul>
        {todos.map((todo) => (
          <li key={todo.id}>{todo.text}</li>
        ))}
      </ul>
      <button onClick={() => addTodo('New Todo')}>Add Todo</button>
    </div>
  );
};

export default TodoList;
```

+ Inmutability is a key concept, you cannot mutate data, look at the following example using `.push()`method to add an element to users array won't re-render our component
![[Pasted image 20240805182622.png]]
#### Pure Functions
+ Functional components mainly are pure functions
+ This components receive props as input and return JSX as output without altering any external state
```javascript
const Counter = ({ count }) => {
  return <h1>{`Count: ${count}`}</h1>;
};
```

#### Composition
+ React embraces composition, allowing developers to build complex UIs by combining simpler components and functions.
+ **Higher-Order Components (HOCs)**: HOCs are functions that take a component and return a new component with enhanced behavior. This promotes code reuse and separation of concerns.
+ **Hooks**: React hooks like `useEffect`and `useState`are firts-class functions
```javascript
import React from 'react';

function withLogger(WrappedComponent) {
  return function(props) {
    console.log('Props:', props);
    return <WrappedComponent {...props} />;
  };
}
```

## References
+ https://janithrs.medium.com/you-should-use-functional-programming-instead-of-oop-when-working-with-react-b12c1ebc5777

