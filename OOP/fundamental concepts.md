# Freestyle, raw version

## OOP Programs comprise objects

- Object encapsulates data , its **state**, together with methods that operate on that data.

- Internal state implementation is invisible to the outside world

- Object invokes its methods when it **receives a request** from a client. This is typically another object

- **Requests/messages** provide the only way to get an object to execute its **methods/operations/commands**

-Object's internal state can be altered only through its **public methods**

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
