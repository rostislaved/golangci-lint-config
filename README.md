<h1> 🛠️ golangci-lint-config </h1>

[[Русская версия]](README-ru.md)

A golangci-lint configuration that enables as many checks as possible.

---
This configuration is currently aligned with: golangci-lint v2.10.4

It should also work with newer versions of golangci-lint, but newer releases may introduce additional settings that are not yet enabled in this configuration.

---

## Why?

* The `golangci-lint` repository doesn’t have a config that enables the maximum number of linters, and even enabling all linters still doesn’t enable all checks within each linter (for example, `gocritic` and `revive`).
* Also, besides individually enabled rules, each linter has its own “settings,” and some of those are disabled by default as well.

---
## What’s in the config

* This config enables the maximum possible number of linters and linter rules.
* For some linters, it also turns on additional settings, for example:

```yaml
# report about assignment of errors to blank identifier: `num, _ := strconv.Atoi(numStr)`.
# Such cases aren't reported by default.
# Default: false
check-blank: true
```

* That said, it’s still an opinionated config, and some linters are disabled. Wherever that happens, there’s a comment explaining why, and you can easily enable them.

---
#### P.S.
Unfortunately, the `golangci-lint` maintainer doesn’t want to add an example config with all default settings, and suggests following the changelog yourself so you don’t miss new rules and settings.
