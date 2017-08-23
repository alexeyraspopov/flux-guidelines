# Flux Guidelines / Core Concepts

Flux pattern is based on several concepts that make it different from well
known MVC pattern.

## Unidirectional data flow

Each piece of system has one particular and unique piece to get data from and
another one to pass data to. There is no intersection between these relations.

## Static subprograms instead of dynamic relations

In the way how the pieces are described they look like stateless pieces of code
with a single entry and an output. However, under the hood those subprograms
are called frequently based on the user's interaction with the system.

## Actions as an activity log

Action as a materialized fact about what happened in the system can be
persisted. List of actions may be used for several techniques that barely
possible to be implemented without it. For example, when a system failure is
observed it can be reported with a list of actions so it can be treated as a
list of steps to reproduce the failure in different environment.

## Deterministic UI state

Concepts described above introduces the way to compute a particular state of
the UI based on a list of actions happened in the system. This creates huge
difference from MVC where you would need to perform some scenario in the way to
get a needed state, where in Flux it happens by a straightforward operation on
data.
