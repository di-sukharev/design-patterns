# Command pattern

Command pattern provides an extra layer between UI and business logic. UI button calls a command and the command calls a business logic. This allows translate requests into objects, log objects, put them in a queue or undo requests.

## Problem

Imagine you have a Button class, which other buttons inherit from. Where to put business logic calls? Different buttons call different business logic.

You could try to move calls to different bussiness apis to sub-classes but there would be a lot of sub-classes then. And if you need to call this businnes api anywhere else you would need to copy the business call code.

## Solution

Move call to business logic to a sub-class (command). All other components which called this business logic directly now should call the command. Command is an intermidiary between UI and businees logic call. Request for business logic is allocated in a separate command, which can be used by different places.

## Scheme

### Invoker (button)

- fields
  - -command: Command // reference to Command, so it can be called in methods
- methods
  - +setCommand(c: Command) // `this.command = c`
  - +executeCommand() // `this.command.execute()`

### Interface Command

- fields
  - …
- methods
  - +execute() // calls Receiver business logic API

### Receiver

- fields
  - …
- methods
  - businessOperation()
