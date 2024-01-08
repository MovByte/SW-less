# Dev Docs

## Implementation

I will write a library with two exports: importScripts and self.addEventListener:

- importScripts - Emulates the importScripts feature in workers. This isn't needed if it is being ran in a webworker.
- addEventListener - This will wrap addEventListener to add fetch events. Emulation of the event handlers will work by intercepting APIs that send HTTP requests and running the handler back on the response. It would require data, to be converted from, to a Response, and back, to be called inside of the original handler.

### For webworkers

The webworker version will be made with [Partytown](https://partytown.builder.io)

## Server-only runtime for proxies

There will be special bundles for CF Workers due to them being nearly identical to the SW API. I might also try to make it possible for the HTML and JS to be rewritten server-side on this platform, for providing better compatiblity.

> If you don't want to use CF Workers, that's fine! You will be able to run these in the standard runtimes through wrangler. I will provide middleware for routers in the other runtimes.

## To use

All you have to do is just create a module script, and inside import all the exports of the bundle

## Bundling

It will compile two bundles:

- Webworker
  - swless.worker.worker.js
  - swless.worker.js
- Normal
  - swless.js
- Server-only
  - server-only/swless.cfworkers.js
  - TODO: ...
