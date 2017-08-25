# Glossary

## Action

A message that represents an event of domain model. Everything that the user
does to domain data is an action. The same as browser events, actions are
plain javascript objects that contain data to describe what happened or what
is going to happen. Usually, action means changes in domain data.

## Action Creator

A function that describes how an action is created. It may use any API (server
requests, browser functions, etc) to make a decision what action should be
created and passed to the dispatcher. One action creator may dispatch more
than one action or action type.

## Dispatcher

Global message queue which is used for dispatching actions. Once dispatched,
action is sent to all dispatcher's listeners. To prevent circular dispatches
and updates that might cause bugs and performance issues, dispatcher's
listeners cannot dispatch new actions.

## Store

Data cache objects. Store can contain a model or collection of models that
should be a part of domain model. Store may listen to the dispatcher and
update its state based on dispatched actions. Store should not introduce any
setters or its data to public API.

## Container

UI components that retrieve data from stores and pass it to children
components. When the user interacts with containers, they should use action
creators to describe user's intent. Once necessary stores are updated,
a container should retrieve new data and update its children.
