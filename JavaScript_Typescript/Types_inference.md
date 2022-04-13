## **Notes around Typescript Types**

- Types are useful when analysing codebase for errors, supporting code readability and enlightment
- Only active during development
- Does not provide performance optimization as it is not active in production

**Explicit Type Annotation**
Semantics we add to tell the Typescript compiler what type of value a variable identifier will refer to.

```javascript
let apples: number = 5;
let speed: string = "fast";
let hasName: boolean = true;
let now: Date = new Date();
let nothing: undefined = undefined;

let fruit: string[] = ["apples", "ornages", "bananas"];

let coords: { x: number, y: number } = { x: 10, y: 15 };

let car: Car = new Car();

let adder:(a:number:b:number)=> number = ( a,b ) => a + b;
```

**Type Inference**

- If we omit type annotation, Typescript will perform implicit type inference, attempting to figure out what kind of type a variable represents

**When type inference occurs**

- If variable declaration and value initialisation are on the same line:

```javascript
const color = ‘red’;// infered automatically
```

- delayed initialisation (see below!)

**When to use type annotation over type inference**

- delayed initialisation:

```javascript
let name;

name = "Kamil";
```

- dealing with non-inferable types - quite common is switching value types dynamically:

```javascript
let numberOrBoolean: Number | Boolean = 1;
```

- When a function returns **ANY** and we want to clarify its return value:
  - It is always best practice to annotate your functions, including annotation of paremeters and return values!

## Any Type

- a fundamental type, just as String or Boolean

- Any type occurs when typescript Compiler has no idea what the resulting type for a particular value is.

- Since we strive to be responsible developers, we should avoid **ANY** at all cost!!!!

- Frequent Occurrence of the following Error message:
  > Variable “....“ implicitly has an “any” type , but a better type may be inferred from usage

It happens when you do something like:

```javascript
let isFound;

// later in code

isFound = true;
```

- to fix this, either perform initialisation at declaration time :

```javascript
let isFound = false;
```

- or annotate the identifier with appropriate type

```javascript
let isFound: Boolean;
```

## Typed Arrays

- Linear Sequences comprising data with common type
- -consider:

```javascript
//supports every value type
	const anyArray = [‘toyota’,’ford’,’ferrari’,3,10,true];


// support value of particular type

const stringArray :string[] = [‘toyota’,’ford’,’ferrari’];

// multiple type support for arrays with UNION TYPES

const multiTypedArray: (string | Date)[]  = [];

//2d arrays
const twoDimensionalArray :string[][] = [];
```
