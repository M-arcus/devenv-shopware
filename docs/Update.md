# Updates

## v2.2.0
* You have to adjust your `devenv.yaml` to
  ```yml
    ...
    kellerkinder:
      url: github:kellerkinderDE/devenv-shopware?ref=v2.2.0
      flake: false
    ...
  ```
* If you want to run multiple projects at the same time, you may have to consider adding `process.implementation = "honcho";` to your `devenv.nix` as the default [process manager in devenv](https://devenv.sh/reference/options/#processimplementation) has changed.  

## v2.1.0
* We support now the newest version of [shopware-cli](https://github.com/FriendsOfShopware/shopware-cli/releases), which be installed directly. To do this, you just need to adjust the following in your `devenv.yaml`
  ```yml
    ...
    kellerkinder:
      url: github:kellerkinderDE/devenv-shopware?ref=v2.1.0
      flake: false
    ...
    froshpkgs:
      url: github:FriendsOfShopware/nur-packages
      inputs:
        nixpkgs:
          follows: "nixpkgs"
    ...
  ```
* The following configuration types have been changed from `string` to `ìnt`: `kellerkinder.httpPort` and `kellerkinder.httpsPort`
  * This is also the case for every other port configuration
* For stability reasons, we use the stable branch `nixos-23.11` instead of `nixos-unstable` in our examples.

## v2.0.0
* We changed the default ports for `http` to `80` and `https` to `443`
  * If you still want to use custom ports, take a look at the [options](Options-Ports.md#kellerkinder-httpPort).
* You have to adjust your `devenv.yaml` to
  ```yml
    ...
    kellerkinder:
      url: github:kellerkinderDE/devenv-shopware?ref=v2.0.0
      flake: false
    ...
  ```
## v1.0.0
* You have to update to devenv version `0.6.3` or higher
* You have to remove `http`, `https` and the ports (e.g. `8000`) from `kellerkinder.additionalServerAlias`
* You have to adjust your `devenv.yaml` to
  ```yml
    ...
    kellerkinder:
      url: github:kellerkinderDE/devenv-shopware?ref=v1.0.0
      flake: false
    ...
  ```
* If your shopware version is below `6.5.x` you might want to add `languages.javascript.package = pkgs.nodejs-16_x;` to your `devenv.nix` due to compatibility.
