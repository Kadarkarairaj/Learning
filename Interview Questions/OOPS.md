There are four principles in OOPS.

## Abstraction
 - Abstraction is the process to hide the internal details and showing only the functionality
 - Abstraction Helps you to simplify the representation of the domain models.
 - Abstraction hides the irrelevant details found in the code.
 - Abstraction solves design level problems
 - Abstraction mainly focus on what should be done
 - Abstraction can be achieved using Interface and abstract class

## Encapsulation
- Wrapping up a data member and a method together into a single unit (in other words class) is called Encapsulation.
- Encapsulation helps to organize the code better
- Encapsulation improves the maintainability, code reability of an application and makes unit testing easy
- Encapsulation solves implementation level problems.
- Encapsulation mainly focus on how should be done.
- Encapsulation can be achieved using access modifiers (public, private, internal, protected)

## Inheritance
- Inheritance is the process of acquiring all the properties and methods of parent class into child class.

- Single 
- Multilevel
- Hierarchical
- Multiple

## Polymorphism
- Polymorphism means one name, many forms.
Polymorphism provides the ability to a class to have multiple implementations with the same name

There are two types of polymorphism
- Compile Time Polymorphism is also known as static binding or early binding ex., method overloading
- Run Time polymorphism is also known as dynamic binding or late binding ex., method overriding

# Access Modifers
- There are four access modifers public, internal, protected, private and six accessibility levels.
    - public
    - internal
    - protected internal
    - protected
    - private protected
    - private

## Solid Principles
- SOLID principles are the design principles that enable us to manage most of the software design problems
### S: Single Responsibility Principle (SRP)
- Every software module should have only one reason to change
- A class should have only one job to do
### O: Open closed Principle (OCP)
- A class is open for extension and closed for modification
### L: Liskov substitution Principle (LSP)
- you should be able to use any derived class instead of a parent class and have it behave in the same manner without modification
### I: Interface Segregation Principle (ISP)
- that clients should not be forced to implement interfaces they don't use. Instead of one fat interface, many small interfaces are preferred based on groups of methods, each one serving one submodule
### D: Dependency Inversion Principle (DIP)
- It is a specific methodology for loosely coupling software modules
- high-level modules/classes should not depend on low-level modules/classes. 
- Both should depend upon abstractions.
- Secondly, abstractions should not depend upon details. Details should depend upon abstractions

More details: https://www.c-sharpcorner.com/UploadFile/damubetha/solid-principles-in-C-Sharp/