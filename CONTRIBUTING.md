# Contributing

Issues and pull requests are welcome. Please report security problems
privately, as [SECURITY.md](SECURITY.md) describes, never in a public issue.

Before you open a pull request, run from the repository root:

```sh
cargo fmt --all --check
cargo clippy --workspace --all-targets -- -D warnings
cargo test --workspace
```

A change to the decoder should also pass the conformance test (see
[README.md](README.md#testing)).

## Licence of contributions

Unless you explicitly state otherwise, any contribution intentionally
submitted for inclusion in this repository by you, as defined in the
Apache-2.0 licence, shall be dual licensed as MIT OR Apache-2.0, without
any additional terms or conditions.

The files derived from the RFC 6386 reference decoder stay under their
BSD-3-Clause notice (see each crate's NOTICE and PROVENANCE.md), and
changes to them are distributed under that notice as well as the above.
