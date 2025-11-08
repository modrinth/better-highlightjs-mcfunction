# MCFunction - a language grammar for highlight.js

This is a fork of the original [highlightjs-mcfunction](https://github.com/TheFireBlast/highlightjs-mcfunction) by FireBlast. The syntax definition has been significantly enhanced by converting the comprehensive [tmLanguage definition](https://github.com/MinecraftCommands/syntax-mcfunction/blob/main/mcfunction.tmLanguage) from the MinecraftCommands/syntax-mcfunction repository into Highlight.js format.

## Features

- Full support for MCFunction syntax including modern (up to 1.21) features
- Macro support with `$(varname)` syntax
- Proper string escape sequence handling
- Enhanced comment types: regular (`#`), heading (`#>`), shebang (`#!`), and block (`##`)
- Accurate UUID, namespace, and selector highlighting
- Resource name validation with namespace:path format
- Coordinate operators (`~`, `^`) and number type suffixes

## Installation

### With pnpm (or npm/yarn)

Since this fork is not published to npm, you need to install it directly from GitHub:

```bash
pnpm install github:modrinth/better-highlightjs-mcfunction
```

Or add it to your `package.json`:

```json
{
  "dependencies": {
    "highlightjs-mcfunction": "github:modrinth/better-highlightjs-mcfunction"
  }
}
```

## Usage

Simply include the Highlight.js library in your webpage or Node app, then load this module.

### Static website or simple usage

Simply load the module after loading Highlight.js. You'll use the minified version found in the `dist` directory. This module is just a CDN build of the language, so it will register itself as the Javascript is loaded.

```html
<script type="text/javascript" src="/path/to/highlight.min.js"></script>
<script
  type="text/javascript"
  charset="UTF-8"
  src="/path/to/highlightjs-mcfunction/dist/mcfunction.min.js"
></script>
<script type="text/javascript">
  hljs.initHighlightingOnLoad();
</script>
```

### With Node or another build system

If you're using Node / Webpack / Rollup / Browserify, etc, simply require the language module, then register it with Highlight.js.

```javascript
var hljs = require("highlightjs");
var hljsMCFunction = require("highlightjs-mcfunction");

hljs.registerLanguage("mcfunction", hljsMCFunction);
hljs.initHighlightingOnLoad();
```

## License

This project is released under the MIT License. See [LICENSE][1] file for details.

## Links

- The official site for the Highlight.js library is <https://highlightjs.org/>.
- The Highlight.js GitHub project: <https://github.com/highlightjs/highlight.js>.
- Learn more about MCFunction: <https://minecraft.gamepedia.com/Function_(Java_Edition)>.

[1]: https://github.com/TheFireBlast/highlightjs-mcfunction/blob/master/LICENSE
