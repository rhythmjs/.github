# Rhythm

Rhythm is a minimal, type-safe middleware kernel for TypeScript, and a small ecosystem of focused packages
built on top of it. A framework should be something you compose, not something you inherit.

## Philosophy

**The onion is the whole framework.** Everything is a middleware: validation, error handling, logging, and
sessions are all the same shape, so they all compose, and your own code is a first-class citizen.

**Types flow with the request.** Whatever a middleware adds to the context, such as a validated body or a
session, is typed in every handler after it. You never cast, and removals fail at compile time.

**Small pieces, honestly separated.** Small packages, one subpath export per module, no barrels. You ship
only what you import; unused features cost nothing.

**Web standards, no lock-in.** Standard `Request` and `Response`, thin adapters for Node.js, Bun, and Deno,
and any Standard Schema validation library. No vendor to marry.

**Explicit beats magical.** No decorators, no containers, no hidden execution order. An application is
built by ordinary function calls, so what runs, and when, is readable in the code itself.

## Links

- [Organization on GitHub](https://github.com/rhythmjs) · [Packages on npm](https://www.npmjs.com/org/rhythmjs)
- [rhythm](https://github.com/rhythmjs/rhythm): the kernel, the router, and the CLI
- [middleware](https://github.com/rhythmjs/middleware): validation, response interception, exception filtering
- [http](https://github.com/rhythmjs/http): cookies, sessions, caching, and request limits
- [security](https://github.com/rhythmjs/security): CORS, CSRF protection, secure headers
- [observability](https://github.com/rhythmjs/observability): logging, request ids, server timing
- [Standard Schema](https://standardschema.dev): the validation specification Rhythm builds on

All packages are released under the [ISC License](https://opensource.org/license/isc-license-txt).
