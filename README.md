# vp8

A VP8 video decoder and encoder in pure Rust, following RFC 6386.

| Crate | What it is | crates.io | Docs |
|---|---|---|---|
| [`vp8-decoder`](crates/vp8-decoder) | A VP8 decoder with no dependencies, conformance-tested on the WebM project's test vectors, with NEON and SSE2 loop filters. | [crates.io](https://crates.io/crates/vp8-decoder) | [docs.rs](https://docs.rs/vp8-decoder) |
| [`vp8-encoder`](crates/vp8-encoder) | A real-time VP8 encoder in safe Rust: rate control, keyframes on request, temporal layers. | [crates.io](https://crates.io/crates/vp8-encoder) | [docs.rs](https://docs.rs/vp8-encoder) |

Each crate's README covers its API, speed, MSRV and how it is checked.

## Versions

vp8-encoder shares vp8-decoder's prediction, transforms and loop filter
through hidden modules that are not a stable API, so it pins vp8-decoder
to an exact version (`=x.y.z`). The two crates are released together, at
the same version.

## Licence

Both crates are `(MIT OR Apache-2.0) AND BSD-3-Clause`: our own code is
MIT OR Apache-2.0 ([LICENSE-MIT](LICENSE-MIT), [LICENSE-APACHE](LICENSE-APACHE)),
and vp8-decoder ports the RFC 6386 Section 20 reference decoder, which is
BSD-3-Clause. See each crate's NOTICE and PROVENANCE.md:
[vp8-decoder](crates/vp8-decoder/NOTICE) ([provenance](crates/vp8-decoder/PROVENANCE.md)),
[vp8-encoder](crates/vp8-encoder/NOTICE) ([provenance](crates/vp8-encoder/PROVENANCE.md)).

## Testing

```sh
cargo fmt --all --check
cargo clippy --workspace --all-targets -- -D warnings
cargo test --workspace
```

The decoder's conformance test decodes the WebM project's VP8 test vectors
and checks the MD5 of every shown frame. The vectors are test data and are
not in this repository; a script downloads them and checks each file's
SHA-256:

```sh
crates/vp8-decoder/scripts/fetch-test-vectors.sh /tmp/vp8-vectors
VP8_TEST_VECTORS=/tmp/vp8-vectors cargo test -p vp8-decoder --release --features conformance
```

`crates/vp8-encoder/scripts/` holds cross-checks against libvpx (through
ffmpeg), Chrome's WebCodecs and a real camera clip's bitrate; each script
says what it needs.

## Issues and security

Report bugs and questions on [Issues](https://github.com/AlakazamLabs/vp8/issues).
Please report security problems privately, as [SECURITY.md](SECURITY.md)
describes, never in a public issue. Contributions are welcome: see
[CONTRIBUTING.md](CONTRIBUTING.md).
