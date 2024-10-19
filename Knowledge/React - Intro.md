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
+ Don't have Business Logic
+ For Titles e.g Design system components
	+ Mucho mejor que poner clases css repetidas en lugares distintos

> Nota: no usar estilos como en el ejemplo, mala practica, mejor usar modulos o styled-components

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
+ Have BL (requirements)

![[Pasted image 20240817184832.png]]
## 4. Hook
+ Fragmento de lógica que representa el ==ciclo de vida== de un componente ==(se crea, ejecuta y muere)=== y es reutilizable
	+ built-in hooks como: useState, useEffect, etc.
	+ custom hooks
+ Empiezan por la palabra `use`
## 5. Conditional Rendering
+ modular components
+ `ternary operator` or `&&`
## 6. Loops: (Render a collection of Items)
+ **key prop** ==don't use index from map== use crypto.randomUUID() o ids gotten from api