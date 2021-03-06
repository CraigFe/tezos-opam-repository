# C implementation of BLS12-381

This library exports Rust functions to the elliptic curve bls12-381 as a C
interface from the pairing crate of
[librustzcash](https://github.com/zcash/librustzcash/tree/master/pairing). The C
functions can then be used to write bindings between different languages.

## Build the library

```
cargo build
```

It will build a static library `librustc_bls12_381.a` in `target/default/`

## Usage

Buffers as `unsigned char*` are passed to each function to write the computation results.

## TODO

- more security like raising exception in Rust, etc when something went wrong. It is not the case for the moment.
- use an additional integer to check if everything went well. `void` is used for the moment.

## Fr and Fq12 representations

- Little endian representation is used.

## Benchmarks

Benchmarks are available. The benches do not include the conversion from and to
C arrays. The results can be used to get the overhead of the binding.


```
cargo +nightly bench
```
