# TypeScript bug reproduction

## Steps to reproduce

Clone and setup the repo

```sh
git clone https://github.com/remcohaszing/typescript-jsdoc-import-bug.git
cd typescript-jsdoc-import-bug
npm ci
```

Build the project

```sh
npx tsc --build
```

Observe that TypeScript emits the following invalid content in `dist/index.d.ts`:

```ts
/**
 * @import {
 *   Program
 * } from 'estree'
 */
/**
 * @param {Program} program
 */
export function compile(program: *   Program): void;
import type { Program } from 'estree';
```
