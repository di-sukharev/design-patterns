# Mediator pattern

Behavioral pattern.

Mediator handles communication between multiple objects and avoids coupling between them.

## Problem

How would you handle form submit if form consists of many fields dependent on each other?
For example: clicking submit button handles validation and invokes saveFormRequest().
You don't want to write form specific code inside input and button components, so what is the way to avoid coupling?

## Solution

The mediator acts as a form state manager. Based on the values passed to it from inputs and buttons, it decides when the validation was successful and when to send the request.

## Scheme

### Interface Mediator

- fields
  - -state
- methods
  - +notify(state) // `this.state = state`

### Class ConcreteMediator implements Mediator

- fields
  - -state
- methods
  - constructor(state)
  - +notify(state) // `this.state = state`
  - …
  - +doSomething() // dependent on the state

### Class Component

- fields
  - mediator: Mediator
- methods
  - onChange() // `this.mediator.notify(this)`

### Client

```javaScript
btn = new component()
checkbox = new component()
input = new component()

mediator = new ConcreteMediator({ btn, checkbox, input })

checkbox.onClick = mediator.notify(checkbox)
input.onChange = mediator.notify(input)


btn.onClick = mediator.doSomething() // submit form
```
