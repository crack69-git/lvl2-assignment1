# Type Narrowing

Type Narrowing is the process of reducing a variable's possible types to a more specific type so that TypeScript can safely access properties and methods associated with that type.

It is commonly used with union types.

For example:
let value: string | number;

# 1.typeof

ex:-

    function processInput(value: string | number): string | number {
    if (typeof value === "string") {
        return value.toUpperCase();
    }

    return value * 10;
    }

# 2.instanceof

Ex:-

    class Dog {
    bark(): string {
        return "Woof!";
    }
    }

    class Cat {
    meow(): string {
        return "Meow!";
    }
    }

    function speak(animal: Dog | Cat): string {
    if (animal instanceof Dog) {
        return animal.bark();
    }

    return animal.meow();
    }

# 3.in

ex:
interface Admin {
name: string;
permissions: string[];
}

    interface User {
    name: string;
    email: string;
    }

    function getInfo(person: Admin | User): string {
    if ("permissions" in person) {
    return `Admin: ${person.name}`;
    }

    return `User: ${person.name}`;
    }
