# State pattern

## Problem

State pattern manages complex if/else logic allowing objects behave differently depending on their state. From the outside object has same API, but the results of using the object are different.

For example object's Shipment method `changeState()` will behave differently in different states: created, delivering, delivered.

1. in 'created' state `changeState()` method can only change state to 'delivering'
2. in 'delivering' state `changeState()` method can only change state to 'delivered'
3. and finally when Shipment is delivered `changeState()` method shouldn't do anything.

## Solution

State pattern moves state dependent logic to diffirent classes and provides a link to the main object (called context) to this classes.

All classes that implement state dependent logic should be based on one single interface describing common fields and methods between different state classes.

## Scheme

### Class Context

- fields
  - state: State
- methods
  - constructor(initState: State) // calling `changeState(initState)`
  - changeState(s: State) // calling `this.state = State; this.state.setContext(this)`
  - doSomething() // calling `this.state.doSomething()`
  - doAnything() // calling `this.state.doAnything()`

### Interface State (describe common methods between different States)

- methods
  - doSomething()
  - doAnything()

### Class ConcreteState implement State (should be more than one)

- fields
  - context // reference to Context, so it can be manipulated via `changeState(nextState)`
- methods
  - setContext(c: Context)
  - doSomething()
  - doAnything()
