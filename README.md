## Typescript W3Schools

### What is TypeScript?
TypeScript is a syntactic superset of JavaScript which adds `static typing`.

This basically means that TypeScript adds syntax on top of JavaScript, allowing developers to add `types`.

> TypeScript being a "Syntactic Superset" means that it shares the same base syntax as JavaScript, but adds something to it.

### Why should I use TypeScript?
JavaScript is a loosely typed language. It can be difficult to understand what types of data are being passed around in JavaScript.

In JavaScript, function parameters and variables don't have any information! So developers need to look at documentation, or guess based on the implementation.

TypeScript allows specifying the types of data being passed around within the code, and has the ability to report errors when the types don't match.

For example, TypeScript will report an error when passing a string into a function that expects a number. JavaScript will not.

> TypeScript uses compile time type checking. Which means it checks if the specified types match `before` running the code, not `while` running the code.

### TypeScript Simple Types
TypeScript supports some simple types (primitives) you may know.

There are three main primitives in JavaScript and TypeScript.

- `Boolean` - true or false values

- `number` - whole numbers and floating point values

- `string` - text values like "TypeScript Rocks"

There are also 2 less common primitives used in later versions of Javascript and TypeScript.

- `bigint` - whole numbers and floating point values, but allows larger negative and positive numbers than the `number` type.

- `symbol` are used to create a globally unique identifier.

### Type Assignment

When creating a variable, there are two main ways TypeScript assigns a type:

- Explicit
- Implicit

In both examples below firstName is of type string

#### Explicit Type
Explicit - writing out the type:
```js
let firstName: string = "Dylan";
```
__Explicit__ type assignment are easier to read and more intentional.

#### Implicit Type
__Implicit__ - TypeScript will "guess" the type, based on the assigned value:
```js
let firstName = "Dylan";
```
> Note: Having TypeScript "guess" the type of a value is called infer.

### TS Special Types
- __Type:any__
```ts
let v: any = true;
v = "string"; // no error as it can be "any" type
Math.round(v); // no error as it can be "any" type
```

- __Type:unknown__
```ts
let w: unknown = 1;
w = "string"; // no error
w = {
  runANonExistentMethod: () => {
    console.log("I think therefore I am");
  }
} as { runANonExistentMethod: () => void}
// How can we avoid the error for the code commented out below when we don't know the type?
// w.runANonExistentMethod(); // Error: Object is of type 'unknown'.
if(typeof w === 'object' && w !== null) {
  (w as { runANonExistentMethod: Function }).runANonExistentMethod();
}
// Although we have to cast multiple times we can do a check in the if to secure our type and have a safer casting
```

- __Type:never__
```ts
let x: never = true; // Error: Type 'boolean' is not assignable to type 'never'.
```

- __Type: undefined & null__
```ts
let y: undefined = undefined;
let z: null = null;
```

### TypeScript Arrays
```ts
const names: string[] = [];
names.push("Dylan"); // no error
// names.push(3); // Error: Argument of type 'number' is not assignable to parameter of type 'string'.
```

#### Readonly
```ts
const names: readonly string[] = ["Dylan"];
names.push("Jack"); // Error: Property 'push' does not exist on type 'readonly string[]'.
// try removing the readonly modifier and see if it works?
```

### TypeScript Tuples
A tuple is a typed array with a pre-defined length and types for each index.

Tuples are great because they allow each element in the array to be a known type of value.

To define a tuple, specify the type of each element in the array:

```ts
// define our tuple
let ourTuple: [number, boolean, string];
// initialize correctly
ourTuple = [5, false, 'Coding God was here'];
// We have no type safety in our tuple for indexes 3+
ourTuple.push('Something new and wrong');
console.log(ourTuple);
```

- Readonly Tuple
```ts
// define our readonly tuple
const ourReadonlyTuple: readonly [number, boolean, string] = [5, true, 'The Real Coding God'];
// throws error as it is readonly.
ourReadonlyTuple.push('Coding God took a day off');
```

- Named Tuples
```ts
const graph: [x: number, y: number] = [55.2, 41.3];
```

- Destructuring Tuples
```ts
const graph: [number, number] = [55.2, 41.3];
const [x, y] = graph;
```