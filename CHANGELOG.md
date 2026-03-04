Version history
==============

### Version 1.0.1
Changed:
* golangci-lint 2.6.0 → 2.10.1
* Instead of explicitly enabling linters and commenting out those that need to be disabled, all linters are now enabled by default (`default: all`), and the ones that should be turned off are explicitly listed under `disable`. The previous approach was used because updating `golangci-lint` would automatically enable newly added linters, potentially breaking backward compatibility. However, since this config is intended to be used with a specific version of `golangci-lint`, this is no longer an issue. The new approach has its advantages: it’s cleaner, and when upgrading to a new version, there’s no need to explicitly add newly introduced linters.
* Disabled `godoclint` — more suitable for libraries.
* Config main language is English

Fixed:
* YAML formatting updated.


### Version 1.0.0
* Initial version