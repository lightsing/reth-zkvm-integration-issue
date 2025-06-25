# reth zkvm integration issue

With all crates `default-features = false`, `reth-codec` feature got enabled somewhere,
cause `reth-zstd-compressors` - `zstd` - `zstd-safe` - `zstd-sys` included in dependency tree.

This cause zkvm toolchain fail to build, since `cc` is not available.

# To check your fix if ok to build

- `grep zstd-sys Cargo.lock` to confirm `zstd-sys` is not in the dependency tree.
- run `cargo openvm build` to see if it works without err. 
  (if you don't have `cargo-openvm`, see https://book.openvm.dev/getting-started/install.html)
