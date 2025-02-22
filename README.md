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
```
let firstName: string = "Dylan";
```
__Explicit__ type assignment are easier to read and more intentional.

#### Implicit Type
__Implicit__ - TypeScript will "guess" the type, based on the assigned value:
```
let firstName = "Dylan";
```
> Note: Having TypeScript "guess" the type of a value is called infer.

