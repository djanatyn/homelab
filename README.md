# homelab
lab notebook and utility scripts for djanatyn's homelab

## cross-compilation

```
# setup
$ nix profile add nixpkgs#zig nixpkgs#cargo-zigbuild
$ rustup target add aarch64-unknown-linux-musl
$ rustup target add x86_64-unknown-linux-musl

# build
$ cargo zigbuild --release --locked --target x86_64-unknown-linux-musl
$ cargo zigbuild --release --locked --target aarch64-unknown-linux-musl

# result
$ file target/aarch64-unknown-linux-musl/release/homelab
target/aarch64-unknown-linux-musl/release/homelab: ELF 64-bit LSB executable, ARM aarch64, version 1 (SYSV), statically linked, stripped
$ file target/x86_64-unknown-linux-musl/release/homelab
target/x86_64-unknown-linux-musl/release/homelab: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, stripped
```
