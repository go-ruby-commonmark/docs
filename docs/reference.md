# Reference

The public API lives at the module root (`github.com/go-ruby-commonmark/commonmark`). It is
**Ruby-shaped but Go-idiomatic**: names mirror Ruby's `commonmark`, while the surface follows
Go conventions — value types, explicit errors, no global state.

## Install

```sh
go get github.com/go-ruby-commonmark/commonmark
```

## Import

```go
import "github.com/go-ruby-commonmark/commonmark"
```

## API reference

The authoritative, always-current API reference is generated from the source by
pkg.go.dev:

- **[pkg.go.dev/github.com/go-ruby-commonmark/commonmark](https://pkg.go.dev/github.com/go-ruby-commonmark/commonmark)**

The module's [README](https://github.com/go-ruby-commonmark/commonmark#readme) carries worked
examples and the full, up-to-date surface. This page intentionally links to those
canonical sources rather than duplicating signatures that could drift out of date.

## Conformance

The parser is **CommonMark spec-complete**: it passes **all 652 / 652
[CommonMark spec v0.31.2](https://spec.commonmark.org/0.31.2/) examples,
byte-exact** — 100%, 0 known gaps. The upstream `spec.txt` is embedded and every
example is run on every CI lane, and a ratchet test fails on any regression, so
full conformance can only be held, never quietly lost.

[![CommonMark spec v0.31.2 652/652](https://img.shields.io/badge/CommonMark_spec_v0.31.2-652%2F652-1a7f37)](https://spec.commonmark.org/0.31.2/)

Behaviour is additionally pinned by a **differential oracle** against reference
Ruby: a corpus is run through both the `ruby` binary and this library and the
results are compared, gated on the reference where relevant and skipping itself
where `ruby` is absent so the cross-arch lanes still validate the library.
