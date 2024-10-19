
# Contexts
> React Context provides us a way to pass data down through the component tree to where we need it without having to manually pass props at every single level. It acts as a global storage space for all your components in your project.

![[Pasted image 20240808104217.png]]

## Use cases
1. When prop drilling gets complicated
2. Managing global state in your app (Global data requirement): login, 
3. Themable components
4. Design Pattern named **Compound Components**
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