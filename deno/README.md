# Deno

A Node alternative with a focus on speed and security.

## Benefits of Deno vs. Node

| Category   | Deno                   | Node           | Winner           |
| ---------- | ---------------------- | -------------- | ---------------- |
| Speed      | Rust, V8, Tokio        | C++            | Deno             |
| Security   | Explicit <sup>1</sup>  | None           | Deno             |
| TypeScript | Supported <sup>2</sup> | Libraries Only | Deno             |
| Tooling    | Built-In <sup>3</sup>  | None           | Tie <sup>4</sup> |
| Libraries  | Some <sup>5</sup>      | Numerous (NPM) | Node             |
| ES Modules | Supported <sup>6</sup>              | Babel Required | Deno             |


<font size="2"> 

1. You must explicity allow network/file/env access (e.g. deno run --allow-net example.ts for network requests).
2. tsconfig.json is not required to start using typescript, but you can still add a config file if you prefer to
3. Deno ships as a single executable file and comes with a bundler, debugger, dependency inspector, documentation generator, formatter, test runner, and linter. Deno can also update itself.
4. Deno provides default tools so you don't have to add a bunch of dependencies to your app; however, people have preferences regarding testing libraries, bundlers, etc. so this depends on the individual.
5. Not all npm libraries work with Deno. Deno doesn't store a local copy of a library in a node_modules folder like Node does. Instead, you import libraries into Deno via a URL (e.g. `import * as log from "https://deno.land/std@0.83.0/log/mod.ts";`). Libraries are cached locally on the next start. Deno provides a list of libraries that have valid URLs at https://deno.land/x.
6. Modules - Deno doesn't use npm or node_modules; instead, Deno imports modules from a URL and then caches them locally. No package.json required. ESModules (import x from y) supported by default (require() not supported). Less bloat and quicker apps ftw!

</font>

## How to Start

#### Installation
```bash
brew install deno
```

#### Basic Example
```bash
deno run https://deno.land/std/examples/welcome.ts
```

#### Basic Server
```typescript
// example.ts 

import { serve } from "https://deno.land/std@0.83.0/http/server.ts";
const s = serve({ port: 8000 });
console.log("http://localhost:8000/");
for await (const req of s) {
  req.respond({ body: "Hello World\n" });
}
```

```bash
deno run --allow-net example.ts

curl http://localhost:8000
```