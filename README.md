# reth zkvm integration issue

With all crates `default-features = false`, `reth-codec` feature got enabled somewhere,
cause `reth-zstd-compressors` - `zstd` - `zstd-safe` - `zstd-sys` included in dependency tree.

This cause zkvm toolchain fail to build, since `cc` is not available.
