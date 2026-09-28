# Rhythm

Rhythm is a minimal, type-safe middleware kernel for TypeScript, and a small ecosystem of focused packages
built on top of it. It exists for people who want to understand every layer of their HTTP stack, and who
believe a framework should be something you compose, not something you inherit.

## Philosophy

**The onion is the whole framework.** Everything in Rhythm is a middleware: a function that does some work,
hands control down the chain, and optionally does more work on the way back up. Request validation,
response transformation, error handling, logging, sessions: none of them are special framework concepts.
They are all the same shape, which means they all compose, and anything you write yourself is a first-class
citizen from the start.

**Types flow with the request.** When a middleware contributes something to the request context, such as a
validated body, a session, or a request id, that contribution is visible in the types of every handler that
runs after it. You never cast, you never guess what a context holds, and removing a middleware tells you at
compile time exactly which handlers depended on it.

**Small pieces, honestly separated.** The ecosystem is deliberately split into small packages, and each
package exports every module by its own subpath rather than through a barrel. You install what you need,
you import what you use, and nothing else ships with your application. A feature you don't use should cost
you nothing: no bytes, no startup time, no reading effort.

**Web standards, no lock-in.** Rhythm speaks the platform's own language: standard `Request` and `Response`
objects, standard headers, standard streams. The same application runs on Node.js, Bun, and Deno through
thin adapters, and validation accepts any schema library that implements the Standard Schema
specification. The framework never asks you to marry a vendor.

**Explicit beats magical.** There are no decorators, no dependency-injection containers, no file-system
conventions, and no hidden execution order. An application is an ordinary value built by ordinary function
calls, so the answer to "what runs, and when?" is always readable in the code that built it.

**Boring on purpose.** Failures answer with plain, predictable JSON. Internals never leak to clients.
Behavior is covered by tests against the real router rather than promised by documentation. The goal is
software you can trust without having to think about it.

## Links

- [Organization on GitHub](https://github.com/rhythmjs) · [Packages on npm](https://www.npmjs.com/org/rhythmjs)
- [rhythm](https://github.com/rhythmjs/rhythm): the kernel, the router, and the CLI
- [middleware](https://github.com/rhythmjs/middleware): validation, response interception, exception filtering
- [http](https://github.com/rhythmjs/http): cookies, sessions, caching, and request limits
- [security](https://github.com/rhythmjs/security): CORS, CSRF protection, secure headers
- [observability](https://github.com/rhythmjs/observability): logging, request ids, server timing
- [Standard Schema](https://standardschema.dev): the validation specification Rhythm builds on
- [Fetch Standard](https://fetch.spec.whatwg.org): the `Request`/`Response` model Rhythm speaks natively

## License

Everything is released under the [ISC License](https://opensource.org/license/isc-license-txt).
