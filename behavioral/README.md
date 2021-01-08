# Behavioral patterns

Behavioral patterns manage clear and effective communication between objects, reducing coupling between objects and classes.

## Chain of responsibility

Creates pipeline of handlers.

## Command

Acts as an intermidiary step between UI and business logic.

## Iterator

Handles iterations of different collections used in one place. Collections can be swapped but abstraction level of iterating stays the same.

## Mediator

Works as a state container which handles complex communication between objects avoiding coupling.

## Memento

Snapshots the current state of an object. Object's state can be later restored from the snapshot.

## Observer

Objects subscribe on events of each other. Subscriber gets notified by Publisher if event occurs.

## State

Object behave differently dependent on current state. Abstract point of view stays the same, state changes internal behaviours.

## Strategy

Client use different algorithms in runtime dependent on current strategy. Separates algorithms into one interface, so abstract point of view stays the same.

## Template method

Separates one single algorithm into steps. Assembles different algoritms combining different steps from the separated algorithm. Avoids code duplication.

## Visitor

Visitor allows to add new features to a program without changing classes these features affect.
