# Access Modifiers in TypeScript OOP

## Introduction

Access Modifiers are used to control how class members are accessed. This helps to organise your code as well as protecting data. Typescript has several Access Modifiers which include public, private and protected. Also there is a readonly modifier to stop a property from being reassigned.

### Explanation

`Public`: Members can be accessed anywhere. This is the default if you don’t specify any access modifier.

```ts
class Student {
  public name: string;
  constructor(name: string) {
    this.name = name;
  }
}
```

`Private`: Members can only be accessed within the class they are created in. This keeps data safe.

```ts
class BankAccount {
  private balance: number = 1000;
  getBalance(): number {
    return this.balance;
  }
}
```

`Protected`: Members can be accessed within the class and subclass. This is useful if you want a child class to have access to a parents property.

```ts
class Employee {
  protected name: string = "Nabil";
}
class Manager extends Employee {
  showName(): string {
    return this.name;
  }
}
```

`Readonly`: Members can be assigned to when declared or in the constructor but can’t be reassigned.

```ts
class Product {
  readonly productId: number;
  constructor(id: number) {
    this.productId = id;
  }
}
```

### Conclusion

Access Modifiers make your object orientated programs easier to maintain. Using public will allow members to be accessible, private will keep information specific to the class, protected will allow access between parent and child classes and readonly will stop values changing.
