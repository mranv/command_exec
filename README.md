# Command Executor

Command Executor is a simple Rust program that executes a given command in the Windows command prompt and returns the output. It takes a single command-line argument and prints the result of the command execution.

## Features

- Executes any command in the Windows command prompt.
- Returns the output of the command.
- Handles both standard output and standard error.

## Usage

### Prerequisites

- Rust installed on your machine. If not, you can download it from [here](https://www.rust-lang.org/tools/install).

### Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/mranv/command_exec.git
    cd command-executor
    ```

2. Build the project:
    ```sh
    cargo build --release
    ```

### Running the Program

To execute a command, run the following in your terminal:

```sh
cargo run -- "your_command"
```

Replace `"your_command"` with the actual command you want to execute. For example:

```sh
cargo run -- "dir"
```

### Example

```sh
$ cargo run -- "echo Hello, World!"
   Compiling command-executor v0.1.0 (path\to\your\project)
    Finished dev [unoptimized + debuginfo] target(s) in 1.0 secs
     Running `target\debug\command-executor.exe echo Hello, World!`
Hello, World!
```

### Code Explanation

- **`executecmd` Function**: This function takes a command string, constructs the full command to be executed in `cmd.exe`, and returns the command's output.
  - It splits the command into a vector of arguments.
  - Executes the command using `Command::new("cmd.exe").args(&cmds).output()`.
  - Captures and returns the standard output or standard error.

- **`main` Function**: This function processes command-line arguments and calls the `executecmd` function.
  - It checks if exactly one argument is provided.
  - Calls `executecmd` with the provided command and prints the result.
  - Prints usage information if the number of arguments is incorrect.

## Contributing

Feel free to open issues or submit pull requests if you have any suggestions or improvements.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to customize the README further according to your preferences and specific requirements.
