# Queue - Abstract Data Type

## What it is ?

- a queue is simply a concept; an idea that enables the arrangment of data in linear sequence.
- storage & retrieval of the dataset strictly abides by the FIFO principle.
- In other words, FIRST ITEM IN --> FIRST ITEM OUT

## Where is the benefit/ use cases ?

- JavaScript engine implements **Event Queue** mechanism to control asynchrony within single stack/process
- Printer jobs are stored inside of a Queue
- supermarket wating lines
- Call Centres

## General Interface

Typical interface of a Stack tends to boil down to these crucial methods:

1. **enqueue(value)** -- adds an element onto the back of the queue
2. **dequeue()** -- removes the element from the front of the queue and returns it
3. **peek()** -- looks at the element at the front of the queue
4. **isEmpty()** returns a boolean value: - **TRUE** if the queue is empty

- **FALSE** if it has at least one element

## Tradeoffs - drawbacks -

- No random access - top or nothing
- No searching through the stack
- No walk through the stack
- **dequeue** operation can be expensive ,especially for larger queues, since each subsqeuent value must have its index position re-calculated again
