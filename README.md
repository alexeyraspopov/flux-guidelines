# Flux Guidelines

A set of guides for building scalable single-page web applications using
unidirectional data flow.

The guides are based on [Facebook's Flux][1] implementation. The examples of UI
code are written in [React][2] however Flux can be used with any other UI layer
implementation.

## Table of contents

 * [Introduction](./Introduction.md)
 * [Glossary](./Glossary.md)
 * [Core Concepts](./CoreConcepts.md)
 * Project Structure
 * Writing Stores
 * Writing Action Creators
 * Fetching & Caching Data
 * Creating Containers
 * Using Immutable Data
 * Writing tests

## Tools and examples

When it comes to development tools configuration, the guides are referring to
[Create React App][3] as a base tool with all the batteries included. This
helps staying focused on the topic and don't repeat guides for a particular
tool which eventually becomes outdated. All examples described in JavaScript
using ES2017. In case you're not familiar with the features in the newest
standards, it's better to start with [Exploring JS][4] project.

## About

This is a non-profit project that aims at popularizing described approach in
building web applications. The guides are based on the author's real-world
experience in using [Flux][1] with [React][2] and [Angular][5].

The project is opened for any contributions (clarifications, updates, fixes,
etc) and is [located][6] on GitHub. If you're interested, please check
[the contributing guidelines][7].

The project is licensed under the [Creative Commons Attribution 4.0][8] license.

 [1]: http://facebook.github.io/flux
 [2]: http://facebook.github.io/react
 [3]: https://github.com/facebookincubator/create-react-app
 [4]: http://exploringjs.com
 [5]: https://angularjs.org
 [6]: https://github.com/alexeyraspopov/flux-guidelines
 [7]: https://github.com/alexeyraspopov/flux-guidelines/blob/master/CONTRIBUTING.md
 [8]: https://github.com/alexeyraspopov/flux-guidelines/blob/master/LICENSE
