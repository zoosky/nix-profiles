# nix-profiles

Library of common nix profiles used in various deployments.

## Including profiles in your nixos configuration

```
let
  profiles = (
    if (builtins.tryEval (import <xtruder/nix-profiles>)).success
    then import <xtruder/nix-profiles>
    else import (builtins.fetchTarball https://github.com/xtruder/nix-profiles/tarball/v0.48)
  );
in {
  imports = profiles.profiles;
}
```

## Defined options

Look into [options.md](options.md) file.
