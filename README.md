# webstate

Global state for the browser. Configure once, access anywhere.

## What is this?

**webstate** is a minimal, zero-dependency JavaScript state library for client-side applications. It provides a single global store with atomic, idempotent get/set operations — no framework lock-in, no build tool requirements, no transitive dependency trees.

It works with React, Vue, Svelte, vanilla JS, or whatever comes next. You bring the rendering; webstate holds the state.

## Why?

Most state libraries are tightly coupled to a specific framework, ship more code than you'd write yourself, or pull in dependencies you didn't ask for. If all you need is a reliable place to put global state — with clean reads, predictable writes, and the ability to subscribe to changes — you shouldn't need a framework-specific solution to get it.

webstate exists because global state is a solved problem that keeps getting re-solved with unnecessary complexity.

## Principles

### Zero dependencies

webstate has no production dependencies. None. Not even TypeScript — it's pure JavaScript. The library you install is the library you run. Dev tooling (test runners, linters) stays in dev where it belongs.

### Atomic operations

Every `get` returns the current value. Every `set` replaces it. There are no partial updates that leave your state in an inconsistent intermediate form. Reads and writes are discrete, predictable operations.

### Idempotent access

Calling `get` ten times returns the same value ten times. Calling `set` with the same value doesn't trigger unnecessary noise. The store behaves the same way regardless of how many times or from where you access it.

### Configure once, access anywhere

You define your store's shape once at initialization. From that point on, any part of your application can read or write state through the same interface — no prop drilling, no context wrappers, no provider hierarchies.

### Framework-agnostic

webstate doesn't know or care what renders your UI. It exposes a subscription mechanism that any rendering library can hook into. First-class bindings for React (and others) can be built as thin adapter layers on top, not baked into the core.

## Designed for

- **Single-page applications** — the primary target. If your app lives in the browser and manages client-side state, this is for you.
- **Multi-framework projects** — share state across micro-frontends or mixed-framework apps without coupling to any one of them.
- **Anywhere JavaScript runs in a browser** — nothing here assumes a specific bundler, framework, or build pipeline.

## Status

Under active development. API is not yet stable.
