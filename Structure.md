# Flux Guidelines / Structure

[Facebook's Flux][1] is [available][2] as a NPM package and can be installed
using:

```bash
npm install --save flux
```

At the initial step of the project, the dispatcher instance should be created.

```javascript
// Dispatcher.js
import { Dispatcher } from 'flux';
export default new Dispatcher();
```

 [1]: http://facebook.github.io/flux
 [2]: https://www.npmjs.com/package/flux
