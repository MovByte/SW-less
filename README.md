# SW-less runtime for proxies

[Dev Docs](./DEV.md)

These will allow any interception proxy to work in different environments by wrapping the SW Apis. This will allow your proxy to work without service workers. It will work by essentially emulating some of the SW apis and It can either run on a web worker, or without any workers at all. This is for environments that don't support service workers. It could also be used for hosting a proxy on sites that don't support external scripts (.js files), external files, or restrict SW registering. Think of [domain fronting](https://github.com/VyperGroup/aero/blob/Unstable/docs/For%20devs%20only/Domain%20Fronting.md). This will allow for countless opportunities for proxies in geographically restricted areas!
