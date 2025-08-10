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

## Shadowing

You can declare a new variable with the same name as a previous variable. Rustaceans say that the first variable is shadowed by the second, which means that the second variable is what the compiler will see when you use the name of the variable. In effect, the second variable overshadows the first, taking any uses of the variable name to itself until either it itself is shadowed or the scope ends. We can shadow a variable by using the same variable’s name and repeating the use of the let keyword as follows:

```rs
fn main() {
    let x = 5;

    let x = x + 1;

    {
        let x = x * 2;
        println!("The value of x in the inner scope is: {x}");
    }

    println!("The value of x is: {x}");
}
```

This program first binds x to a value of 5. Then it creates a new variable x by repeating let x =, taking the original value and adding 1 so the value of x is then 6. Then, within an inner scope created with the curly brackets, the third let statement also shadows x and creates a new variable, multiplying the previous value by 2 to give x a value of 12.

Shadowing is different from marking a variable as mut because we’ll get a compile-time error if we accidentally try to reassign to this variable without using the let keyword. By using let, we can perform a few transformations on a value but have the variable be immutable after those transformations have been completed.