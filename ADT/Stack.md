# Stack - Abstract Data Structure 

## What it is ?

- a stack is simply a concept; an idea that enables the arrangment of data in linear sequence.
- storage & retrieval of the dataset strictly abides by the LIFO principle.
- the principle imposes  the crucial design constraint;it is only ever  permissable to alter the top of the stack. 
- In other words,    LAST ITEM IN --> FIRST ITEM OUT


## Where is the benefit/ use cases ?

- Imposing LIFO constraint establishes controlled data access
- Support for UNDO / REDO actions 
- JavaScript Call Stack uses stack to manage and thread through various invocation contexts  - the topmost element refers to the currently active context.
- Reversing a Sequence of data ,for instance, a string reversal can be implemented using stacks. 
- Browser History can be thought of as a series of stackframes. 

## Visual Representation:

Visual Representation of Stacks: ![Alt][1]

[1]: /images/Slack(1).png "Stack Birds-eye view"


## General Interface 

Typical interface of a Stack tends to boil down to these crucial methods:
1. **push()**
2. **pop()**
3. **peek()**
4. **isEmpty()**

