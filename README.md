# Rust Timestamp Generator

A small Windows command-line utility written in **Rust** that generates a timestamp in the format:

```text
YYYYMMDD_HHMMSS
```

The generated timestamp is automatically copied to the **Windows clipboard**, making it easy to paste into filenames, documents, notes, or other applications.

## Project Goals

This project started as a small, practical utility, but it also served as an experiment in learning **Rust**.

One of the goals was to investigate Rust as a language for building small, compiled utilities that can produce standalone executables and potentially be built for **multiple operating systems and platforms**.

The timestamp program was deliberately simple so that the focus could be on learning the Rust development workflow — including Cargo, dependencies, compilation, release builds, and platform considerations — rather than on building a complicated application.

## Example

Running the program produces:

```text
20260918_083745
```

The timestamp is also immediately available on the Windows clipboard.

## Features

* Written in Rust
* Uses the computer's local date and time
* Generates sortable timestamps
* Format: `YYYYMMDD_HHMMSS`
* Automatically copies the result to the Windows clipboard
* Produces a standalone Windows `.exe`
* No Python installation required to run the compiled program

## Requirements

To build the project, you need:

* Windows
* Rust
* Cargo

Install Rust using [rustup](https://rustup.rs/).

Verify the installation:

```powershell
rustc --version
cargo --version
```

## Building

Clone the repository:

```powershell
git clone https://github.com/sydkahn/timestamp.git
cd timestamp
```

Build the project:

```powershell
cargo build
```

The executable will be located at:

```text
target\debug\timestamp.exe
```

## Release Build

For the optimized release version:

```powershell
cargo build --release
```

The executable will be:

```text
target\release\timestamp.exe
```

The release executable can be copied to another Windows computer and run without installing Rust.

## Running

From the project directory:

```powershell
.\target\release\timestamp.exe
```

Example output:

```text
20260918_083745
```

The same value is automatically placed on the Windows clipboard.

## Dependencies

The project uses:

* **chrono** — date and time handling
* **arboard** — clipboard access

Cargo manages these dependencies automatically.

## Why This Format?

The timestamp uses the order:

```text
YEAR MONTH DAY HOUR MINUTE SECOND
```

For example:

```text
20260918_083745
```

Because the largest time unit comes first, files named with these timestamps will sort chronologically when sorted alphabetically.

For example:

```text
20260917_220000
20260918_073000
20260918_083745
20260918_120000
```

## Project Structure

```text
timestamp/
├── Cargo.toml
├── Cargo.lock
├── README.md
├── .gitignore
└── src/
    └── main.rs
```

The compiled `target` directory is intentionally excluded from Git.

## AI-Assisted Development

This project was developed with the assistance of AI tools.

AI was used as a development partner for exploring Rust and its tooling, working through implementation approaches, writing and revising code, troubleshooting errors, and explaining Rust concepts and compiler messages.

The project remained a hands-on learning exercise: the requirements, goals, testing, decisions, and final integration were directed and reviewed by the author.

## License

This project is provided for personal use and experimentation.

