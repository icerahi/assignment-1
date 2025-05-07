# 1. Difference between **Types** and **Interface** in Typescript.

In typescript, both **type** and **interface** used a lot and both do similar kinds of stuff but there are some difference.
Let's see the difference.

## \*\*type

**type** are used to define types for both **primitives** and **non-primitives** values. That means we can use `type` with value like `string`,`number`,`boolean`, also with `array`,`tuple`,`object` and even more.

### Example with types

```ts
type Name = string;
type Age = number;
type isSingle = boolean;

//with array
const cities: string[] = ["Dhaka", "Vilnius", "Moscow"];

//with object
type User = {
  name: string;
  email: string;
  age: number;
};
```

So, we can say `type` is flexible and we can use it with more others place.

## Interface

Let's talk about **Interface** now. **Interface** is usually use with non-primitive data. We can't use interface with primitive types like `string` or `number`.

### Example

```ts
interface User {
  name: string;
  email: string;
  age: number;
}
```

So, if we try like

```ts
interface Name=string // it will not work
```

Typescript will not satisfied with the above code where we set interface for string.
But it will not complain if we try with **objects** or **classes**

So, Finally `type` is more flexible and can be used both primitive and non-primitive data, on the otherhand, `interface` is mostly for objects.



# 2.Using Union and Intersection Types in TypeScript

As, we already know Typescript give us type safety,along with more cool features and two of them are **Union** and **Intersection** types.
These can be helpful when we are working with data that maybe in different shape or we wan to combine multiple types together.

## Union Types (`|`)
A **union type** is like `or` type such as it says 'a variable can be hold either this type or that type'

Let's clarify with example:
```ts
type Id=string|number
//here we specifying by the union operator that Id will be either string type or number type

let userId:Id;

userId=101; //no problem
userId="icerahi" //no problem
userId=true // not allowed
```
So, from the example above we can say union types are super flexible when date can be hold multiple types.

We can also use union with custom types:
```ts
type Kutta={
    name:string;
    bark():void
}

type Bilai={
    name:string;
    mew():void;
}

type Pet = Kutta | Bilai;
```

## Intersection Types (`&`)

An **intersection type** combines multiple types in to one. it say's like 'This must be both of those types'.

Example:
```ts
type Name={
    name:string;
}
type Age={
    age:number;
}

type Person=Name & Age

const user:Person={
    name:"imran",
    age:10,
}
```
This union operator is super useful when we are trying to build up complex types from multiple smaller ones.


Finally, We use **union types** (`|`) when a value can be one **of multiple types** and **intersection types** (`&`) when a value needs to be a **combination of multiple types**.