# Core Concepts

Flux pattern is based on several concepts that make it different from well
known [MVC pattern][1]. These concepts explain the nature of relations between
entities and layers in the system. Each of them can be effective in isolation
from others, but together they shape the pattern in the way we know it.

## Unidirectional data flow

Each piece of a system has one particular and unique piece to get data from and
another one to pass data to. There is no intersection between these relations.
However, the type of relations is different in each particular case. Containers
_pull_ data from stores, when stores _react_ on actions from the dispatcher.
It aims at satisfying the rules of [loose coupling][2] and [high cohesion][3].

A set of connections can be represented as a circle:

    Store         →      Container
      ↑                      ↓
    Dispatcher    ←      Action Creator

Entities have a specific type of relations that determine the scope of
knowledge about each other:

 1. Containers _pull_ data from Stores
 2. Containers _push_ data to Action Creators
 3. Action Creators _push_ actions to Dispatcher
 4. Stores _react_ on Dispatcher

Here are the key points:

 * Dispatcher does not know about any piece of the system
 * Stores only know about Dispatcher and use it as a single source of truth to
   mutate their state
 * Action Creators know how to produce actions and dispatch them
 * Containers (as a UI layer) know where to get data and how to react to the
   user's input

## Static subprograms instead of dynamic relations

In the way how entities are described, they look like stateless pieces of code
with a single entry and an output. However, under the hood, those subprograms
are called frequently based on the user's interaction with the system. This
achieved by generalizing the data flow and keeping the mechanism separately
from the domain knowledge.

## Actions as an activity log

Action as a materialized fact about what happened in the system can be
persisted. List of actions may be used for several techniques that barely
possible to be implemented outside of the pattern. For example, when a system
failure is observed it can be reported with a list of actions so it can be
treated as a list of steps to reproduce the failure in a different environment.

## Deterministic UI state

Concepts described above introduces the way to compute a particular state of
the UI based on a list of actions happened in the system. This creates a huge
difference from MVC where you would need to perform some scenario in the way to
get a needed state, where in Flux it happens by a straightforward operation on
data.

 [1]: https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
 [2]: https://en.wikipedia.org/wiki/Loose_coupling
 [3]: https://en.wikipedia.org/wiki/Cohesion_(computer_science)
