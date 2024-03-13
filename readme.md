# Node

[Nix Node Wiki](https://nixos.wiki/wiki/Node.js)

1. Create `.envrc` file in the root of the project
2. Add the following to the `.envrc` file

```sh
use nix
```

3. Copy or link the node-shell.nix file to the root of the project
4. Add the dependencies to the `node-shell.nix` file

```nix
in pkgs.mkShell {
  packages = with pkgs; [
    nodejs
    nodePackages.npm

    # Add your dependencies here

    # keep this line if you use bash
    pkgs.bashInteractive
  ];

```

4. Run `direnv allow` to apply the changes
