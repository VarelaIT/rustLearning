# Learning Rust

## Rust commands

Verify Rust installation

```bash
rustc --version
```
### Updating and Uninstalling
Once Rust is installed via rustup, updating to a newly released version is easy. From your shell, run the following update script:

```bash
rustup update
```

To uninstall Rust and rustup, run the following uninstall script from your shell:

```bash
rustup self uninstall
```

#### Cargo

```bash
cargo --version
```

Creating a new Cargo project.

```bash
cargo new folder_name
```

Building a Cargo project.

```bash
cargo build
```

Cargo build also downloads depdendecies.

Running a Cargo project.

```bash
cargo run
```

#### Cargo Release

```bash
cargo build --release
```
This command will create an executable in target/release instead of target/debug. The optimizations make your Rust code run faster, but turning them on lengthens the time it takes for your program to compile.

### Cargo update

When you do want to update a crate, Cargo provides the command update, which will ignore the Cargo.lock file and figure out all the latest versions that fit your specifications in Cargo.toml. Cargo will then write those versions to the Cargo.lock file

```bash
cargo update
```
