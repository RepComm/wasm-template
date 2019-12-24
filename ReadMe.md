# Wasm Template

Written because I finally got the result I wanted:

Minimalistic boilerplate.

## Structure:
`template.html` loads index.js as a module

`index.js` imports `./wasm/template.mjs`

`index.js` instantiates the module it imported.

`main` is auto-called from `template.c`

Boom, done, goodnight.

Compilation is up to you.
`build.sh` runs `env.sh`, which calls `emsdk_env.sh` (sets up environment variables temporarily) from my setup of emsdk.

## Notes
`env.sh` won't work for you unless you point it at your copy of `emsdk_env.sh` from emscripten sdk.

Also, `source` is used to say "run in this bash context" and not a separate child shell. Otherwise the environment is flushed away when `env.sh` is finished.