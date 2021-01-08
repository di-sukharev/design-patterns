# Visitor pattern

Bahavioral pattern.

Visitor allows to add new features to a program without changing classes these features affect.

## Problem

Suppose you want to add new functionality, but adding the feature violates open-closed principle — adding new functionality requires changing lots of methods by adding some code. The other problem is that your feature may not fit in a concept or SRP principle of some class or all classes.

## Solution

Visitor solves the problem by putting the feature into a separate class without modifying existing classes.

We don't add new functionality to existing classes or their interface if they share one.
New feature goes to Visitor class, and all existing classes `accept(Visitor)` with the new functionality.

## Scheme

### Interface Element

- methods
  - +accept(v: Visitor)

### Interface Visitor

- methods
  - visit(el: ElementA)
  - visit(el: ElementB)
  - visit(el: ElementC)
  - …

### Client

```javaScript
visitorA = new VisitorA() // VisitorA implements interface Visitor
visitorB = new VisitorB() // VisitorB implements interface Visitor

button = new ElementA() // ElementA implements interface Element
input = new ElementB()  // ElementB implements interface Element

// can be done via for…of loop
button.accept(visitorA) // calls the new functionality from visitorA.visit(b: Button)
input.accept(visitorB) // calls the new functionality from visitorB.visit(i: input)
```
