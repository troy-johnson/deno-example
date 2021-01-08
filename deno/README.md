# Deno

A Node alternative with a focus on speed and security.

## How to Start

```typescript

```

## Benefits of Deno vs. Node

| Category   | Deno                       | Node           | Winner           |
| ---------- | -------------------------- | -------------- | ---------------- |
| Speed      | Written in Rust, V8, Tokio | Written in C++ | Deno             |
| Security   | Explicit <sup>1</sup>      | None           | Deno             |
| TypeScript | Supported <sup>2</sup>     | Libraries Only | Deno             |
| Tooling    | Built-In <sup>3</sup>      | None           | Tie <sup>4</sup> |
| Libraries  | Some <sup>5</sup>          | Numerous (NPM) | Node             |
| ES Modules | Supported                  | Babel Required | Deno             |

1. You must explicity allow network/file/env access (e.g. deno run --allow-net example.ts for network requests).
2. tsconfig.json is not required to start using typescript, but you can still add a config file if you prefer to
3. Deno ships as a single executable file and comes with a bundler, debugger, dependency inspector, documentation generator, formatter, test runner, and linter. Deno can also update itself.
4. Deno provides default tools so you don't have to add a bunch of dependencies to your app; however, people have preferences regarding testing libraries, bundlers, etc. so
5. 

- Modules - Deno doesn't use npm or node_modules; instead, Deno imports modules from a URL and then caches them locally. No package.json required. ESModules (import x from y) supported by default (require() not supported). Less bloat and quicker apps ftw!
