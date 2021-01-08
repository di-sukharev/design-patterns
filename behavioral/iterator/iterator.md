# Iterator pattern

Behavioral pattern.

Iterator provides single interface to iterate over data structures with different implementation.

## Problem

Sometimes you need to iterate over different collections in one code place, eg method. Different collections iterated differently and you don't want to polute the method with if/else ot switch statements to implement different iteration algorithms. For example: Tree can be iterated by bfs or dfs, graph an list are iterated differently as well.

## Solution

Each collection should have an Iterator. Iterator implements the iteration algorithm abstracting the details. So, the Client simply call `Iterator.next()` to iterate over the collection.

## Scheme

### Interface Iterator

- methods
  - +getNext()
  - +hasMore(): bool

### Interface Collection

- methods
  - +createIterator(): Iterator

### Class ConcreteCollection implemets Collection

- fields
  - … internal fields …
- methods
  - +createIterator(): Iterator
  - … internal methods …

### Class ConcreteIterator implemets Iterator

- fields
  - -collection: ConcreteCollection
  - -iterationState
- methods
  - constructor(c: ConcreteCollection) // `this.collection = c`
  - +getNext()
  - +hasMore(): bool

### Client

```javaScript
tree = new TreeCollection
treeIterator = tree.createIterator()

iterator.next()
iterator.next()
iterator.next()

list = new ListCollection
listIterator = list.createIterator()

iterator.next()
iterator.next()

…
```
