# spec

## Central Git repository

Hosted on GH. Contains the packages, package definitions, and metadata & package scripts for every specific version.

All scripts should be executables.

Repositories are:

- core
  - core-testing
- community
  - community-testing

```txt
- :package-name
  - package.toml (package metadata)
  - :version
    - metadata.toml (version metadata)
    - package (script to make package)
    - preinstall (script that runs before install)
    - postinstall (script that runs after install)
  - :version
    - metadata.toml
    - package
    - preinstall
    - postinstall
  ...
```

## Decentralized mirror

```txt
- :repository
  - :package-name
    - :version
      - :package-name-:version-intel.tar.xz
      - :package-name-:version-silicon.tar.xz
    - :version
      - :package-name-:version-intel.tar.xz
      - :package-name-:version-silicon.tar.xz
  ...
```

## Git repository with mirror information

```txt
- mirrors
  - :mirror-name
    - info.toml
  - :mirror-name
    - info.toml
  ...
```
