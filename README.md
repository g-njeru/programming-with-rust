# programming-with-rust

My own implementation of the four programs from the tour in Chapter 2 of
*Programming Rust, 2nd Edition* (Jim Blandy, Jason Orendorff, Leonora F. S. Tindall — O'Reilly, 2021).

Everything here is written by hand from the book while reading it, not copied from the official sample code.

- Book: <https://www.oreilly.com/library/view/programming-rust-2nd/9781492052586/>
- ISBN: 9781492052586
- Errata: <https://www.oreilly.com/catalog/errata.csp?isbn=0636920258049>
- Official sample code: <https://github.com/ProgrammingRust/examples>
- Mandelbrot variants (single-threaded, bands): <https://github.com/ProgrammingRust/mandelbrot>

## Programs

| # | Path | What the book builds it to show | Status |
|---|------|--------------------------------|--------|
| 1 | `projects/gcd` | CLI calculation over command-line arguments, unit tests; core types and traits | todo |
| 2 | `projects/actix-gcd` | Web server; string handling, closures, error handling | todo |
| 3 | `projects/mandelbrot` | Fractal plotter; generic functions, pixel buffers, concurrency | todo |
| 4 | `projects/grep` | Robust command-line tool over files; file APIs, regular expressions | todo |

Update the status column as each program is finished.

## Layout

```
Cargo.toml           workspace root
projects/
  gcd/               program 1
  actix-gcd/         program 2
  mandelbrot/        program 3
  grep/              program 4
.github/workflows/   CI: fmt, clippy, test
```

Each project is a standalone Cargo package that also belongs to the root workspace.

## Working on it

```sh
cargo build --workspace
cargo test --workspace
cargo run -p gcd
cargo fmt --all
cargo clippy --workspace --all-targets -- -D warnings
```

Add dependencies to each project's `Cargo.toml` as the book introduces them (the web server needs an HTTP framework, the plotter needs an image writer, the grep tool needs a regex crate).

## Toolchain

The book targets the Rust 2021 edition and was written against Rust 1.50. Local development uses a much newer toolchain, so a few book snippets (notably around `panic!` formatting, `try` blocks, and newer trait bounds) will need adjusting.

## License

MIT — see [LICENSE](LICENSE).
