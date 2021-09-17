# spec

Packages available in Pakket are seperated in 2 repositories. These are:

- core
  - core-testing
- community
  - community-testing

The Core repository is maintained by Pakket contributors and has the most important packages, like programming languages, compilers, the most-used tools and more.

The Community repository is inspired from Arch Linux's AUR. Everybody can publish packages to the Community repository, and people can vote out packages if they are duplicates, malware, etc. Pakket has first-party support for the Community repository, but it must be enabled by the user.

## Central Git repository (core)

Hosted on GH. Contains the packages, package definitions, metadata & package scripts for every specific version.

All scripts should be executables.

```txt
- packages
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

A mirror hosts all the binaries. There are two tiers of mirrors, tier 1 and tier 2 mirrors.

- Tier 1 mirrors
  - High bandwidth, storage and computing power. Sync directly from the official Pakket mirror. Mirrors must be selected.
- Tier 2 mirrors
  - Sync from tier 1 mirrors.

Everybody can start a tier 2 mirror, but you must submit it to become a official mirror.

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
