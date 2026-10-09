# Fork-specific changes

This fork follows [bucanero/apollo-lib](https://github.com/bucanero/apollo-lib).
`main` mirrors upstream. Intentional fork changes and this document belong on
`develop` only.

## Workflow branch filters

The current fork-specific configuration changes are limited to these workflows:

- [Build binaries](.github/workflows/build.yml)
- [Run tests](.github/workflows/tests.yml)
- [Build WebAssembly](.github/workflows/build-wasm.yml)

Each workflow adds the following filters so pushes run on `develop` and pull
requests run when they target `develop`:

```yaml
push:
  branches:
    - develop
pull_request:
  branches:
    - develop
```

All other content in these workflows matches upstream, including
`repository_dispatch` with the `run_build` event type, jobs, build commands,
test commands, and artifacts. All other workflow files also match upstream.
There are currently no fork-specific source-code or test-implementation changes.

## Maintenance

When merging upstream into `develop`, preserve these branch filters and update
this document if the intentional differences change. Keep `main` aligned with
upstream; start upstream contribution branches from `main` so this document and
the fork-specific filters remain on `develop`.
