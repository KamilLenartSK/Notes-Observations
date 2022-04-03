# Freestyle, raw version

## OOP Programs comprise objects

- Object encapsulates data , its **state**, together with methods that operate on that data.

- Internal state implementation is invisible to the outside world

- Object invokes its methods when it **receives a request** from a client. This is typically another object

- **Requests/messages** provide the only way to get an object to execute its **methods/operations/commands**

-Object's internal state can be altered only through its **public methods**

- Objects expose behaviour and hide internal state / structure !

## Method signature

- Every method defined as part of an object specifies:
  - method's name
  - **parameters** ,representing all the objects or data it accepts
  - the return value

## Object Interface

- Object's interface characterises what type of object are permitted to be passed into the object

- Set of all signatures defining object methods are collectively called the interface of the object

- Two objects adhering to the same interface can have vastly unique implementation details

## OBJECT CLASS VS OBJECT TYPE

- Object's class specifies how an object is implemented. In other words, it specifies object's internal state and signature of its methods

- Object's type only refers to its interface , listing set of requests to which the object in question can respond to
  - object components can have many types
  - interfaces can contain other interfaces as subsets
    - a type is a subtype of another , if its interface blueprint is contained within an interface of its supertype

## Abstract Classes

- Abstract class **cannot be instantiated** directly!
- Abstract class defines **common interface** for its subclasses
- Abstract class will defer the implementation for some of its methods to its subclasses

  - **abstract methods**
    - they are declared on the abstract class but lack implementation details
    - concrete class must implement the abstract operations
    - absract methods establish a contract

- manipulating object solely in terms of interfaces defined within the **abstract classes**
  - clients remain unaware of the specific implementation details of objects they use ,as long as the object implements the interface
  - clients are only aware of the abstract classes defining the interfaces
    - white-box problems -- **visibility of parent methods**

## Class Inheritance vs Interface Inheritance

- Class inheritance:

  - Code reuse and sharing mechanism
  - Particular object has its internal representation completely influenced by another object's internal implementation
    - extending state AND behavior
  - a mechanism for extending application's functionality by reusing old application state / exiting code functionality
  - class inheritance happens at compile-time

- Interface Inheritance:
  - what object type can be substituted in place of another object

## Program to an interface not implementation !!!

### Object Composition

- composition keeps classes focused on a **single task**

- implementation details remain private as objects communicate through their interfaces

- To this end, composition requires objects to respect interfaces of other objects

- new functionality is attained by assembling different object to work together, in turn, creating sophisticated objects from the composites

- composition happens at runtime
- **HAS a relation** rather than **IS a**

- **Delegation in Composition**
  - two or more objects as participants
  - receiving object delegates tasks to its delegate
  - the receiving object passes itself to the delegate - **dependency injection via interface** - to let the delegated operation refer to the receiving object

## Acquaintance vs Aggregation

- aggregation implies that an object is responsible for another object

- in turn, they have identical lifespans
- tight coupling is created

- Conversely, acquaintance implies weaker relationship between objects
  - one object merely knows of another object
  - objects may pass requests to one another but are not responsible for one another's behavior

## Law of Demeter

- Module / Object should not know about the innards of the object it manipulates
- If method F is defined on object C, THEN method F should only call methods of these :

  - Object C
  - Object created by F
  - Object passed as an argument to F
    - Object held as instance variable inside C

- The above reinforces that Objects should talk to their FRIENDS not STRANGERS !
- Additionally, never ask an object to do something, always delegate the action to it via DI

## Data Transfer Objects

- A class/ object with public fields only without methods !
- Very useful for communicating with Databases

## Active Record

- Special Kind of DTO
- Contains navigational methods (find,save)
