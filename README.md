# BasicOS

A small operating system written in C and assembly, using the 32-bit RISC-V ISA. 

The OS is compiled with the LLVM cross-toolchain, boots through OpenSBI, and runs on the QEMU 'virt' RISC-V board, allowing the OS to be built, loaded and debugged with no physical hardware required.


## Features 

- Command-line shell
- Process switching and scheduling
- Exception handling
- System calls
- Device drivers (read/write)
- File system

## Installation (MacOS)

1. Clone the repository to your desired location.

2. Install Homebrew and run the following command to install LLVM, LLD, and QEMU:

    ```Bash
    brew install llvm lld qemu
    ```

3. Add LLVM binutils to the terminal search `PATH`:

    ```Bash
    export PATH="$PATH:$(brew --prefix)/opt/llvm/bin"
    ```

4. Check that this was successful:

    ```Bash
    which llvm-objcopy
    ```

    This should return `/opt/homebrew/opt/llvm/bin/llvm-objcopy`.

## Usage

1. Navigate to the root directory.

2. Run the OS:

    ```Bash
    ./run.sh
    ```

    If the OS booted successfully, you will see the following message in the command-line:

    ```Bash
    Successful boot of BasicOS.
    ```

3. To write a hardcoded message to `test1.txt`, enter `writefile`.

4. To read the message, enter `readfile`. 

5. To shutdown the OS and leave the virtual environment, press `Ctrl + A`, followed by `C` and then enter `q` into the QEMU debug console.