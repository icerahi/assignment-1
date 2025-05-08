# 1. Difference Between **Types** and **Interface** in TypeScript

In TypeScript, both **type** and **interface** are used widely and serve similar purposes, but there are key differences between them. Let's see these differences.

## **type**

**type** is used to define types for both **primitive** and **non-primitive** values. So, we can use `type` with values like `string`, `number`, and `boolean`, as well as with `array`, `tuple`, `object`, and more.

### Example with Types

```ts
type Name = string;
type Age = number;
type IsSingle = boolean;

// With array
const cities: string[] = ["Dhaka", "Vilnius", "Moscow"];

// With object
type User = {
  name: string;
  email: string;
  age: number;
};
```

From this, we can see that `type` is flexible and can be used in different different situation.

## **interface**

Now, let's discuss **interface**. **Interface** is primarily used with non-primitive data. Unlike `type`, we cannot use `interface` with primitive types like `string` or `number`.

### Example

```ts
interface User {
  name: string;
  email: string;
  age: number;
}
```

However, if we attempt something like this:

```ts
interface Name = string; // This will not work
```

TypeScript will raise an error because interfaces cannot be assigned to primitive types. They are designed for objects, classes, and other complex structures.

In summary, `type` is more versatile and can handle both primitive and non-primitive data, while `interface` is primarily intended for object.

---

# 2. Using Union and Intersection Types in TypeScript

As we know, TypeScript provides type safety with powerful features like **union** and **intersection** types. These are useful when working with data that can be in different structure or when combining multiple types.

## Union Types (`|`)

A **union type** is like an `or` condition, that allow a variable to hold one of multiple possible types.

Let's check this with example:

```ts
type Id = string | number;
// Here, we specify that `Id` can be either a string or a number.

let userId: Id;

userId = 101; // Valid
userId = "icerahi"; // Valid
userId = true; // Invalid
```

Union types are highly flexible when working with data that can be of multiple types.

We can also use union with custom types:

```ts
type Kutta = {
  name: string;
  bark(): void;
};

type Bilai = {
  name: string;
  mew(): void;
};

type Pet = Kutta | Bilai;
```

## Intersection Types (`&`)

An **intersection type** combines multiple types into one, meaning the value must satisfy all the combined types.

Example:

```ts
type Name = {
  name: string;
};

type Age = {
  age: number;
};

type Person = Name & Age;

const user: Person = {
  name: "imran",
  age: 10,
};
```

Intersection types are specially useful when making complex types by merging multiple types.

---

Finally, We use **union types** (`|`) when a value can be one **of multiple types** and **intersection types** (`&`) when a value needs to be a **combination of multiple types**.
