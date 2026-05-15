# fortrun

`fortrun` is an experimental build/run helper for Fortran projects.

Current status: on hold. The repository contains useful caching, CLI, module
scanning, and FPM integration experiments, but it is not the active path for the
Lazy Fortran compiler bootstrap.

## Intended Role

`fortrun` should eventually be a runner/orchestrator:

- run standard Fortran files through existing compilers
- run Lazy Fortran or Infer-mode scripts through FortFront/`ffc`
- cache build artifacts safely
- discover local module dependencies
- integrate with package/build metadata

It should not own the language frontend or native backend. Those belong to:

- [fortfront](https://github.com/lazy-fortran/fortfront): frontend and
  transformation
- [ffc](https://github.com/lazy-fortran/ffc): compiler driver and backend
- [standard](https://github.com/lazy-fortran/standard): target language-mode
  specification

## Current Priorities

Open issues track the work that still matters:

- reduce noisy CLI output
- verify cache behavior with stronger tests
- move standard/language documentation out to `standard`
- decide whether web-style module imports belong here
- align generics/trait behavior with LFortran compatibility

Until `ffc` has a working executable subset, `fortrun` should stay focused on
runner ergonomics and avoid implementing compiler behavior itself.

## Build

```bash
fpm build
```

## Status

Experimental. Expect APIs and behavior to change.
