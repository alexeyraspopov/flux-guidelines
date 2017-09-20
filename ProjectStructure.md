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

 [1]: https://github.com/facebookincubator/create-react-app
 [2]: http://facebook.github.io/flux
 [3]: https://www.npmjs.com/package/flux
