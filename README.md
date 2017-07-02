<h1 align="center">ReasonablyTyped</h1>

<pre align="center">
  $ npm install --global reasonably-typed
</pre>

<h4 align="center"><i>Converts Flow library definitions to Bucklescript interfaces</i></h4>

<hr>

```
retyped

Commands:
  compile [files...]  Generate BuckleScript interfaces from a file

Options:
  --version     Show version number                                    [boolean]
  --help        Show help                                              [boolean]
```

This will generate a Bucklescript interface file for every library definition given. For example,
to generate interfaces from flow-typed, run:

```
$ retyped compile --flow-typed
```

For a single file, run:

```
$ retyped compile my-flow-lib.js
```

See the example directory for usage details.

For more information, run with `--help`.

# Usage as a library

ReasonablyTyped also exports a library for use! See the example below:

```js
// lib-usage.js
import * as ReasonablyTyped from 'reasonably-typed'

const libSrc = fs.readFileSync('lib.js').toString()
const bsInterface = ReasonablyTyped.compile(libSrc)
```

### `format (code: string) => string`

Formats a block of code using `refmt`

### `compile (code: string, filename?: string) => string`

Compiles a libdef, formats the result, and handles errors cleanly

# Roadmap

- [x] Basic types like `string`
- [x] Function types
- [x] Record types
- [ ] Literals as types
- [x] Union types
- [ ] Instersection types
- [x] Named types
- [x] Optional parameters
- [x] Classes
- [ ] Generics
- [ ] Built-ins like Promises and React
