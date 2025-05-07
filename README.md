# Difference between **Types** and **Interface** in Typescript.

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
