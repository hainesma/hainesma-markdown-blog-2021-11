# OOP Principles and SOLID Principles

## The Four Pillars of Object-Oriented Programming

### Abstraction

Abstraction refers to hiding unnecessary details from the user and only showing essential features.

### Encapsulation

Encapsulation refers to putting related code into its own class and then restricting access to that class. In C#, access modifiers (`public` or `private`) can control whether a property of an object can be modified by other parts of the program.

### Inheritance

Inheritance refers the passing of data and functionality from a parent class to a child class. This removes redundant code by allowing for subtypes that contain all the properties of the base class.

### Polymorphism

Polymorphism refers to objects of different classes being accessible through the same interface.


## SOLID Principles

The idea of these principles is to create code that will scale well and be easy to add to.

### Single Responsibility

Each class should have only one responsibility. This allows for easier testing of the class and for easier organization of the program.

If a class has multiple responsibilities, and the nature of one of those responsibilities changes, it could affect the way the class performs the others.

### Open-Closed

Open for extension, closed for modification. This prevents the introduction of bugs by preventing the modification of existing code.

### Liskov Substitution

Parent classes can be substituted with their child classes.

### Interface Segregation

Larger (general) interfaces should be split into smaller (specific) interfaces, so that classes using the interfaces only have to import the methods they need. This minimixes overhead of unused methods.

### Dependency Injection

“classes should depend on abstraction but not on concretion”

Hide the actual implementation of class A from the class B.

This keeps classes loosely coupled.

