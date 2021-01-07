# Memento (snapshot)

Memento pattern says how to save and undo/reuse object state.

## Problem

Imagine you make code editor and implement undo feature. You need to store previous editor state somewhere, so user can go back to the previous state pressing `Ctrl+Z`.

How would you do that feature avoiding violation of main principles?

## Solution

Memento pattern creates snapshot of the Editor's State saving it to History list. Saved States can later be used from `History.pop()` method to restore State via `Editor.restore(s: State)`.

## Interfaces

### Class Originator (Editor)

- fields
  - content: String
- methods
  - createState(): Memento
  - restore(s: Memento)

### Class Memento (State)

- fields
  - content: String

### Class Caretaker (History)

- fields
  - states: Memento[]
- methods
  - push(s: Memento)
  - pop()

## Scheme

TODO
