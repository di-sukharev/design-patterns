# Behavioral patterns

Behavioral patterns manage clear and effective communication between objects, reducing coupling between objects and classes.

## Chain of responsibility

Creates pipeline of handlers which process some request sequentially.

## Command

Acts as an intermidiary step between UI and business logic. Decouples Sender from Receiver via extra Command layer. Command dispatches objects, objects as actions can be logged, stopped, undone.

## Iterator

Handles iterations of different collections used in one place. Collections can be swapped but abstraction level from iteration point of view stays the same.

## Mediator

Works as a state container which handles complex communication between objects avoiding coupling.

## Memento

Snapshots the current state of an object. Object's state can be later restored from the snapshot.

## Observer

Objects (Subscribers) subscribe on events of one object (Publisher). Subscribers are notified by Publisher if it state changes.

## State

Object behave differently depending on current state. Abstract point of view stays the same, state changes internal behaviours.

## Strategy

Client use different algorithms in runtime dependent on current strategy. Separates algorithm into steps, strategies combine the steps in different order or override some steps. Abstract point of view stays the same, strategies can be swapped at runtime.

## Template method

Separates one single algorithm into steps. Assembles different algoritms combining different steps from the separated algorithm. Avoids code duplication.

## Visitor

Visitor allows adding new features to a program without changing classes these features affect.
