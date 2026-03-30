# Cargo Test

Execute all unit and integration tests and build examples of a local package.

[![CI](https://github.com/Kristories/cargo-test/actions/workflows/main.yml/badge.svg)](https://github.com/Kristories/cargo-test/actions/workflows/main.yml)

## Usage

Action metadata is available in [`action.yml`](https://github.com/Kristories/cargo-test/blob/main/action.yml).

```yaml
on:
  push:
  pull_request:

jobs:
  test_job:
    runs-on: ubuntu-latest
    name: Testing
    steps:
      - uses: actions/checkout@v4
      - uses: dtolnay/rust-toolchain@stable
        with:
          toolchain: stable
      - uses: Swatinem/rust-cache@v2
      - name: "Test local rust"
        uses: Kristories/cargo-test@v1
        with:
          manifest-path: './example-rust/Cargo.toml'
```

## Release

Create and maintain a major tag so users can track non-breaking updates:

```bash
git tag -a v1 -m "Release v1"
git push origin v1
```

For a new major version, create a new major tag (for example `v2`) and keep patch/minor tags (`v1.1.0`, `v1.2.0`) for changelog clarity.

## License

The MIT License (MIT). Please see the [license file](LICENSE.md) for more information.