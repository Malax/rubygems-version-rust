# Rubygems Version Parser

A rust implementation of Ruby's `Gem::Version` logic.

Based off of Ruby's `Gem::Version` logic from version `3.4.0.dev` of Rubygems:

- Implementation: https://github.com/rubygems/rubygems/blob/ecc8e895b69063562b9bf749b353948e051e4171/lib/rubygems/version.rb
- Spec: https://github.com/rubygems/rubygems/blob/ecc8e895b69063562b9bf749b353948e051e4171/test/rubygems/test_gem_version.rb

Minor differences between this implementation and target implementation may exist.

## Installation

Add this to your `cargo.toml`:

```toml
rubygems_version = { git = "https://github.com/malax/rubygems-version-rust" }
```

## Usage

```rust
use std::str::FromStr;
use rubygems_version::Version;

let version = Version::from_str("1.0.0").unwrap();
assert!(version < Version::from_str("2.0.0").unwrap());
```

The result may return a `rubygems_version::VersionError::InvalidVersion` result if a valid version cannot be created from the input string. This mirror's `Gem::Version`'s own validation logic.

## Development

```
$ cargo test
```

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/malax/rubygems-version-rust. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [code of conduct](https://github.com/malax/rubygems-version-rust/blob/main/CODE_OF_CONDUCT.md).

## License

The library is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the this project's codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/malaz/rubygems-version-rust/blob/main/CODE_OF_CONDUCT.md).
