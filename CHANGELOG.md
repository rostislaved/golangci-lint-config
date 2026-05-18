Version history
==============

### Version 1.2.0
Changed:
* golangci-lint: 2.11.4 → 2.12.2
* makezero: enforces using append (and not c-style for loops)
* forbidigo: restrict fmt.Print\println and log.Fatal everywhere, but panic only in main and os.Exit everywhere except main
* wsl_v5: add rules: after-block, after-decl, after-defer, after-go, cuddle-group
* revive: import-alias-naming and package-naming don't allow SCREAMING_CASE now
* formatters/gofumpt: enable extra-rules
* formatters/gci: imports now are grouped in sections 
* formatters/swaggo: disabled

### Version 1.1.0
Changed:
* golangci-lint: 2.10.1 → 2.11.4
* Minor version now reflects golangci-lint updates, patch version - config-only changes
* YAML formatting normalized
* Extended comments for revive settings

Added:
* revive:
    * package-naming (flatcase, SCREAMINGCASE, snake_case) - enforces consistent package naming, allows common non-camel formats
    * use-any - replaces interface{} with any
    * comment-spacings - requires space after "//"
    * unhandled-error (with exclusions) - enforces error handling, ignores known safe cases (fmt.Print*, bytes.Buffer.Write*, etc.)
    * import-alias-naming (flatcase, snake_case) - enforces consistent alias style for imports
    * deep-exit - detects hard exits (os.Exit, log.Fatal) inside functions
    * intrange - suggests range-based loops where applicable

Updated:
* revive/unhandled-error exclusions (bytes.Buffer.Write.*)

* Disabled:
* nolintlint (unstable behavior)
* gosec:
    * G705 (XSS via taint) - acceptable when responses are properly encoded (e.g. JSON)
    * G117 (secrets exposure via marshaling) - too noisy for typical use cases
    * G703 (path traversal via taint) - requires manual validation instead

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