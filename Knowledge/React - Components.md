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
