# Template method pattern

Template method pattern manages algorithms that have similar code in general, but some steps are different. These pattern separates different steps into sub-classes without changing it general structure.

## Problem

You have code like this:

```javaScript
initSomething() // same code
instance = new Class(load) // same code
question = 'some question' // different code
answer = instance.askJohn(question) // different code
print(question, answer) // same code
```

And you have code like this:

```javaScript
initSomething() // same code
instance = new Class(load) // same code
question = 'any question' // different code
answer = instance.askSteve(question) // different code
print(question, answer) // same code
```

So you probably don't want to write same code twice, this is the problem Template Method pattern solves.

## Solution

The solution is to split the algorithm into separate methods and call them step by step in one template method.

## Scheme

### Class AbstractClass

- methods
  - templateMethod()
  - step1()
  - step2()
  - step3()
  - step4()

### Class ConcreteClass1 extends AbstractClass

- methods
  - step3() // @override
  - step4() // @override

### Class ConcreteClass2 extends AbstractClass

- methods
  - step1() // @override
  - step2() // @override
  - step3() // @override

### Client

Example of how code is used

```javaScript
concreteAlgorithm1 = new concreteClass1()
concreteAlgorithm1.templateMethod()

concreteAlgorithm2 = new concreteClass2()
concreteAlgorithm2.templateMethod()
```
