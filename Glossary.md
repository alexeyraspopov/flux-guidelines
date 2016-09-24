# Flux Guidelines / Glossary

### Action

A message that represents an event of domain model. Everything that the user
does to domain data is an **action**. The same as browser events, actions are
plain javascript objects that contains data to describe what happened or what
is going to happen. Usually, action means changes in domain data.

### Dispatcher

Global message queue which is used for dispatching actions. Once dispatched,
action is sent to all dispatcher's listeners. To prevent circular dispatches
and updates that might cause bugs and performance issues, dispatcher's
listeners cannot dispatch new actions.

### Store

Data cache objects. Store can contain a model or collection of models that
should be a part of domain model. Store may listen to the dispatcher and
update its state based on dispatched actions. Store should not introduce any
setters or its data to public API.

### View

UI components that retrieve data from stores and pass it to children
components.
