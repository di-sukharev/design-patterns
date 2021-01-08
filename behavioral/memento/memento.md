# Memento or Snapshot pattern

Memento pattern says how to save and undo/reuse object state.

## Problem

Imagine you make code editor and implement undo feature. You need to store previous editor state somewhere, so user can go back to the previous state pressing `Ctrl+Z`.

How would you do that feature avoiding violation of main principles?

## Solution

Memento pattern creates snapshot of the Editor's State saving it to History list. Saved States can later be used from `History.pop()` method to restore State via `Editor.restore(s: State)`.

## Scheme

### Class Originator (Editor)

- fields
  - -content: String
- methods
  - +setContent(c: String) // `this.content = c`
  - +createState(): Memento
  - +restore(m: Memento)

### Interface Memento (State)

- fields
  - -content: String
- methods
  - +getContent(): String

### Class Caretaker (History)

- fields
  - -states: Memento[]
- methods
  - +push(m: Memento)
  - -pop()

### Client

```javaScript
originator = new Originator()
caretaker = new Caretaker()

originator.setContent('something')
caretaker.push(originator.createState())

originator.setContent('anything')
caretaker.push(originator.createState())

originator.setContent('something more')
caretaker.push(originator.createState())

originator.restore(caretaker.pop()) // `Ctrl+Z`

originator.setContent('anything more')
caretaker.push(originator.createState())

originator.restore(caretaker.pop()) // `Ctrl+Z`
```

---

TODO: add scheme image
