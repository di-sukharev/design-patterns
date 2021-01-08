# Observer pattern

Behavioral pattern.

Observer pattern allows one objects to observe other objects, waiting for an event they subscribed for.

## Problem

Suppose buyer wants to buy a book from seller, but there is no book in shop now. So, buyer somehow has to find out if the book is available. Seller could notify all shop clients about this book if it's available, but this would be spammy. On the other hand buyer could call the seller everyday and ask if book is available, but this would be inefficient.

## Solution

Buyer subscribes to sellers notification list via public API, and when the book is available — seller sends to buyer a message.

## Scheme

### Class Publiser

- fields
  - -subscribers: Subscriber[]
  - -mainState // changes to the state should invoke `notifySubscribers()` method
- methods
  - +subscribe(s: Subscriber) // `this.subscribers.add(s)`
  - +unsubscribe(s: Subscriber) // `this.subscribers.remove(s)`
  - +notifySubcribers() // `for s of this.subscribers: s.notify()`
  - +mainBusinessLogic() // changes mainState

### Interface Subscriber

- methods
  - +notify()

### Client

```javaScript
s = new Subscriber()
publiser.subscribe(s)

publiser.doSomethingThatChangesState()
publiser.notifySubscribers()
```
