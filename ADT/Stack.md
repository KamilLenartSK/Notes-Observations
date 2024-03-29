# Stack - Abstract Data Type

## What it is ?

- a stack is simply a concept; an idea that enables the arrangment of data in linear sequence.
- storage & retrieval of the dataset strictly abides by the LIFO principle.
- the principle imposes the crucial design constraint;it is only ever permissable to alter the top of the stack.
- In other words, LAST ITEM IN --> FIRST ITEM OUT

## Where is the benefit/ use cases ?

- Imposing LIFO constraint establishes controlled data access. In turn the data becomes hard to corrupt.
- Support for UNDO / REDO actions - a feature common in text editors.
- JavaScript Call Stack uses stack to manage and thread through various invocation contexts - the topmost element refers to the currently active context.
- Keeping track of recursive calls can be handled by Stacks.
- Reversing a Sequence of data ,for instance, a string reversal can be implemented using stacks.
- Parsers use stack to validate syntax correctness. matching bracket pair etc..
- Browser History can be thought of as series of stackframes.
- Calculators keep intermediate values inside of stack ADT ---> postfix notation

## Visual Representation:

![Stack Visual Depiction](images/Stack.png)

## General Interface

Typical interface of a Stack tends to boil down to these crucial methods:

1. **push()** -- adds an element onto the top of the stack
   - Time Complexity : O(1)
   - Space Complexity : 0(1)
2. **pop()** -- removes the element from the top of the stack and returns it
   - Time Complexity : O(1)
   - Space Complexity : 0(1)
3. **peek()** -- looks at the element at the top of the stack
   - Time Complexity : O(1)
   - Space Complexity : 0(1)
4. **isEmpty()** returns a boolean value: - **TRUE** if the stack is empty
   - Time Complexity : O(1)
   - Space Complexity : 0(1)
5. **isFull()**

- **FALSE** if it has at least one element

## Possible implementation (using **Arrays**)

```javascript
class ArrayStack {
  constructor() {
    this.stack = [];
    this._size = 0;
  }

  get size() {
    return this._size;
  }
  isEmpty() {
    return this.size() === 0;
  }
  peek() {
    if (!this.isEmpty()) {
      return this.stack[this.size() - 1];
    }
  }
  pop() {
    this._size--;
    return this.stack.pop();
  }

  push(element) {
    this._size++;
    this.stack.push(element);
  }
}

export default ArrayStack;
```

## Tradeoffs - drawbacks -

-No random access - top or nothing
-No searching through the stack
-No walk through the stack
