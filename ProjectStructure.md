# Project Structure

This guide assumes [Create React App][1] is used as a base tool for a project.
This allows to focus on Flux without diving into details related to tools
configuration and decisions. [CRA][1] covers all necessary aspects, so
a developer can just start working on the application code.

Covered Flux implementation has all batteries included, so there is no reason
to implement them from scratch.

[Facebook's Flux][2] is [available][3] as a NPM package and can be installed
using:

```bash
npm install --save flux
```

At the initial step of the project, the dispatcher instance should be created.
It will be used as a main message bus, the middle part of whole messaging
process in the system.

```javascript
// src/Dispatcher.js
import { Dispatcher } from 'flux';
export default new Dispatcher();
```

This is it, no more bootstrap required.

You already can start working on required domain logic, however, let's cover
some conventions that help the project scale and be consistent.

There is a controversial topic on how files should be organized: either by
their type (components, controllers, styles) or by the feature they belong to.
This guide will stick to the second option because of several reasons.

When a system has a folder per module type (stores, components, containers,
styles, etc), it ends up having fixed number of folders but every each of them
will include dozens (or even hundreds) files that touching different aspects of
the system. There is no clear vision of a separate subsystems and no scope
defined for isolated graphs of dependencies.

Having a folder per feature (or just a set of modules focused at a particular
part of the system) introduces the ability to work on a feature in isolation.
This means less time to find necessary modules, explore the system peace by
peace, and having defined patterns of dependencies for new features.

 [1]: https://github.com/facebookincubator/create-react-app
 [2]: http://facebook.github.io/flux
 [3]: https://www.npmjs.com/package/flux
