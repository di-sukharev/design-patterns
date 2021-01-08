# Chain of responsibility (CoR) pattern

Behavioral pattern.

CoR creates a pipeline which handles a request step by step in a chain manner.
Pipeline consists of handlers, each handler decide whether request should go to the next handler or stop at the current handler.

## Problem

Suppose you handle a HTTP request. You want to process the request sequentually. First request should be validated, then you want to authenticate user and do something else in the end. You could hardcode the process in a procedural way in some request handler, but this isn't scalable, you would need to duplicate the code in all other handlers which have the same pipeline.

Also hardcoding the pipeline process in a class leads to coupling and lots of if/else spaghetti.

## Solution

Pipilene is separated into handlers. Each handler has `handle()` method and link to a next handler. Client initiates all handlers in a chain and runs them in a loop via single method.

## Scheme

### Interface Handler

- fields
  - -next: Handler | null // link to the next pipeline handler
- methods
  - +setNext(h: Handler) // `this.next = h`
  - +handle() // calls `if next is not null: next.handle()`

### Client

```javaScript
handler1 = new Handler(1)
handler2 = new Handler(2)
handler3 = new Handler(3)
handler4 = new Handler(4)

handler1.setNext(handler2)
handler2.setNext(handler3)
handler3.setNext(handler4)
```
