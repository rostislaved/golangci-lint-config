Version history
==============

### Version 1.1.0
* golangci-lint 2.11.1 -> 2.11.4
* later on minor version bump will mean golangci-lint version bump, patch version bump -> just patch (change of configuration)
* YAML formatting updated.
* Added comments on many revive settings
* enable: revive/package-naming package name validation (only flatcase (and SCREAMINGCASE) and snake_case_names are allowed)
* enable: revive/use-any interface -> any check (modernize fix it automatically anyway)
* enable: revive/comment-spacings triggers when there is no space after "//"
* enable: revive/unhandled-error
* enable: revive/import-alias-naming. Enforces the use of flatcase or snake_case for import alias names
* enable: revive/deep-exit. Triggers on functions like os.Exit() or log.Fatal()
* enable: intrange (modernize fix it automatically anyway)
* disable buggy nolintlint
* Added exclusion for revive/unhandled-error: bytes.Buffer.Write.*
* disable: G705, G117, G703

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