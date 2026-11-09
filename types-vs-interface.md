# Type Aliases vs. Interfaces in TypeScript

## Introduction

In TypeScript we can create type definitions via `type` Aliases or `interfaces`. Whilst the two are similar, they have different features which should be noted to help you make a clear and maintainable decision.

## Detailed Explanation

Interfaces are typically used to define the shape for an object or class. Interfaces can be extended and you can merge/extend interface with the same name:

```ts
interface User {
  id: number;
  name: string;
}

interface Admin extends User {
  permissions: string[];
}

const admin: Admin = {
  id: 1,
  name: "Mina",
  permissions: ["manage-users"]
};
```

A type alias can also used to define object shapes too, but it can also represent unions, intersections, primitives types, tuples, and more.

```ts
type Status = "pending" | "approved" | "rejected";

type Contact = {
  email: string;
};

type Customer = User & Contact;
```

`Status` is a union of specific string values whilst `Customer` is an intersection of two object shapes. This isn’t possible to do in the same way using an interface.

Interfaces can be merged. If you declare another interface with the same name as an existing one it will merge the properties into the original interface. This can be useful if you want to extend some types from a library but can also cause confusion if you accidentally create duplicate interfaces. Type Aliases cannot be merged.

## Conclusion

If you want to define a contract for objects, particularly ones that may be extended or implemented by a class then use an interface. If you need to use unions, intersections, tuples, primitives or simply wish to give a name to a combination of types then use a type alias. For simple object shapes either can be used so try to be consistent throughout your project.
