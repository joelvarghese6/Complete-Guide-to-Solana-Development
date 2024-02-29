# Complete Guide to Solana Developement

## Setup 💻
This section will help you set up your Developing environement.

### 1. Installing Dependencies

Just because Rust compiles and builds your software into a binary that can run for the computer architecture we specify, we need to install some OS-level dependencies on our machine.

#### Dependencies for Windows
You can get started with Solana on Windows with WSL, the Windows subsystem for Linux. WSL allows you to run Linux software easily on Windows using a lightweight VM that instantly starts when you need it.

First start with installing WSL on your system. Be sure to restart your computer when installation is done, then continue this guide.

```
wsl --install
```

After installing WSL and restarting your computer, open a new Linux terminal session using WSL:
```
wsl
```

For the remainder of this guide and your Solana development using WSL, you will run all your commands, Solana builds, and program deployments inside this Linux terminal (except where otherwise noted in this guide).
If you are using VS Code as your code editor of choice, we recommend you follow this tutorial on the VS Code website to properly configure VS Code and WSL together. This will give you the best developer experience.

#### Dependencies for Linux
Install the following dependencies on your Linux system:
```
sudo apt-get install -y \
    build-essential \
    pkg-config \
    libudev-dev llvm libclang-dev \
    protobuf-compiler libssl-dev
```

#### Dependencies for macOS
In macOS, build tools are given by Xcode command line tools, which you can download it directly from Apple. You will likely need to sign in with your Apple ID to download.
You can check if the Xcode CLI is installed via this command:
```
xcode-select -p
```
If you don't see a path returned, you need to install the CLI tools.

There are different ways to install Xcode CLI tools:
1. Installing via your terminal using the following command:
```
xcode-select --install
```
2. Download the installer and install it with a graphical interface Apple Developer Tools

### Install Rust
The Rust programming language is a multi-paradigm, general-purpose programming language that emphasizes performance, type safety, and concurrency.
Using rustup, the official Rust version installer and manager, we will install rustc (the compiler for rust) and cargo (the package manager for rust) all at once.

Using the following command, we can install and configure the Rust tooling on your local system. The following command will automatically download the correct binaries needed for your specific operating system:
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
```
As part of this Rust installer, Rustup will also configure your terminal's PATH to include the rust toolchain.

After the installation is complete, restart your terminal or run the following command to manually refresh your new PATH settings to make the rust tooling (like cargo) available:
```
source ~/.bashrc
```

### 3. Install the Solana CLI
For local development, including compiling your Solana programs, you will need to install the Solana CLI. This command-line tool suite provides all the commands needed to perform common tasks, like:

- creating and managing file-system Solana wallets/keypairs,
- connecting to Solana clusters,
- building Solana programs,
- and deploying your programs to the blockchain

