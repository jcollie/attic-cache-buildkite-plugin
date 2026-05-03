<!-- SPDX-FileCopyrightText: © 2024 Jeffrey C. Ollie <jeff@ocjtech.us> -->
<!-- SPDX-License-Identifier: MIT -->

# Enable Nix caching on your Buildkite agent using Attic

## Example

```yml
secret:
  - ATTIC_CACHE_TOKEN

steps:
  - command: nix build .#myproject
    plugins:
      - jcollie/attic-cache#v1.0.0:
          server: example
          endpoint: https://cache.example.org/
          cache: example-cache
```

## Configuration

## Developing

### BuildKite tests

To run the tests:

```shell
podman run -it --rm -v "$PWD:/plugin:ro" docker.io/buildkite/plugin-linter --id jcollie/attic-cache
```
