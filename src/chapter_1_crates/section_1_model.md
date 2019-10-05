# Model

`dawn-model` is a crate of only serde models defining the Discord APIs with
no implementations on top of them or functions to work with them.

These are in a single crate for ease of use, a single point of definition,
and a sort of versioning of the Discord API. Similar to how a database
schema progresses in versions, the definition of the API also progresses in
versions.

The types in this crate are reproducible: deserializing a payload into a
type, serializing it, and then deserializing it again will work.

Defined are a number of modules defining types returned by or owned by
resource categories. For example, `gateway` are types used to interact with
and returned by the gateway API. `guild` contains types owned by the Guild
resource category. These types may be directly returned by, built on top of,
or extended by other crates.

### Installation

This crate requires Rust 1.31+.

Add the following to your `Cargo.toml`:

```toml
dawn-model = { git = "https://github.com/dawn-rs/dawn" }
```

### Features

`dawn-model` has a single feature, `serde-support`. By default it is enabled.
This enables serde support of the models, which brings in four dependencies:

- `serde`
- `serde_json`
- `serde-mappable-seq`
- `serde_repr`

If you don't need serde support, you can disable it:

```toml
[dependencies]
dawn-model = { default-features = false, git = "https://github.com/dawn-rs/dawn" }
```

### Links

*source*: <https://github.com/dawn-rs/dawn/tree/master/model>

*docs*: <https://docs.rs/dawn-model>

*crates.io*: <https://crates.io/crates/dawn-model>
