# Node

[Nix Node Wiki](https://nixos.wiki/wiki/Node.js)

1. Create `.envrc` file in the root of the project
2. Add the following to the `.envrc` file

```sh
use nix
```

3. Copy or link the shell.nix file to the root of the project
4. Add the dependencies to the `node-shell.nix` file

```nix
{ pkgs ? import <nixpkgs> {} }:

pkgs.mkShell {
  buildInputs = [
    pkgs.nodejs
    pkgs.nodePackages_latest.vercel
    pkgs.nodePackages_latest.typescript

    # keep this line if you use bash
    pkgs.bashInteractive
  ];
}

```

4. Run `direnv allow` to apply the changes
