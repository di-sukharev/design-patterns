# Strategy pattern

Behavioral pattern.

Strategy pattern combines algorithms with a single interface, which allows you to replace algorithms with each other at runtime.

## Problem

Imagine you create a map app. Map app should be able to create a route from A to B. Depending on transport algorithms can be different, eg bicycle has its own bikeway, car goes by the road and you can always go by foot.

So, depending on transport algorithm of create route feature is different and you don't want to polute the Client with if/else or switch code cascades.

## Solution

Separate different algorithms into classes implementing the same interface.

## Scheme

### Class Context

- fields
  - -strategy: Strategy
- methods
  - +setStrategy(s: Strategy) // `this.strategy = s`
  - +doSomething() // `this.strategy.doSomething(data)`

### Interface Strategy

- methods
  - +doSomething(data)

### Class ConcreteStrategy implements Strategy

- fields
  - -strategy: Strategy
- methods
  - +setStrategy(s: Strategy) // `this.strategy = s`
  - +doSomething() // `this.strategy.doSomething()`

### Client

```javaScript
someStrategy = new SomeConcreteStrategy()
context.setStrategy(someStrategy)
context.doSomething()

anyStrategy = new AnyConcreteStrategy()
context.setStrategy(anyStrategy)
context.doSomething()
```
