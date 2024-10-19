+ Compilado
+ superset de javascript
+ `.ts`
+ autocompletado en el editor de codigo
# Intro
## Primitive Types
+ boolean
+ string
+ number
+ any (ojo) <- tipo por defecto en JavaScript
## Inferencia de Tipos
+ Una vez declaras una variable con un tipo primitivo, TS infiere el tipo y vigila que nunca usemos otro
```typescript
const text = "This is text";
```
## Declaración explicita de tipos
```typescript
const n1: number = 123;
```

## Funciones
```typescript
function multiplyBy2(arr: Array<number>){
	const newArr = arr.map( item => item*2)
}
```

## Objetos
+ Usar interfaces o types
```typescript
const person = {
	name: "Alberto",
	age: 16,
	gender: "Male"
}

type Person = {
	name: string,
	age: number
	// propiedad opcional
	// tipo stricto o "Male" o "Female"
	gender?: "Male" | "Female"
}

// Recomendado para funciones y propiedades de React
interface PersonI {
	name: string,
	age: number
	// propiedad opcional
	// tipo stricto o "Male" o "Female"
	gender?: "Male" | "Female"
} 

// los tipos tienen herencia
type Programmer = {
	language: "Javascript" | "Typescript"
}

// operaciones de conuntos: unión, intersección, diferencia
// union de tipos
type ProgrammerPerson = Person & Programmer;

function addOneToAge(person: any){
	person.age += 1;
}
```

## Funciones genéricas / Template Functions
```typescript
function findById<T>(arrar: T, index: number): T | undefined {
	const found = array.find( (elemnt, elementIndex) => index === elementIndex);
	return found;
}
```

## Interfaces
Acts as a contract by enforcing a particular shape on a class or a specific type on a function or variable.  
Classes that “implement” another class must declare all the properties present in the class they implement.
# Especifico para react
+ `tsx` para componentes

## Props
```typescript
type Props = {
	name: string,
	age: number
}

export default function PersonCard({name, age}: Props){
	//...
}
```

## Hooks
```typescript
const [person, setPerson] = useState<Person>({
	name: "Alberto",
	age: 16
})
```

## Eventos
+ Change event de react
+ para el handleChange

```typescript
function handleChange(event: ChangeEvent<HTMLInputElement>){
	setInputValue(event.target.value);
}
```

# OOP in Typescript

# Type Assertion

# Narrowing

# Satisfies Operator
