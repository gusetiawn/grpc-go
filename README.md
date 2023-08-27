# grpc-go
 grpc with go by github.com/gusetiawn

## Installation on macOS

**Install Command Line Tools:** If you haven't installed Command Line Tools for Xcode, you will need to install them first. You can run the following command in Terminal:
```bash
xcode-select --install
```

**Install Homebrew:** Once the Command Line Tools are installed, you can install Homebrew with the following command in Terminal:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Installation Verification:** Once the installation is complete, you can verify the Homebrew installation by running the command:
```bash
brew --version
```

**Adding Homebrew to PATH:** When you install Homebrew, its installation directory is usually not automatically added to your system path (PATH). This means you have to add them manually so that Homebrew commands can be accessed from anywhere in Terminal.

O**pen .zshrc File:** You can use the nano command to open a .zshrc file. Type the following command in Terminal:
```bash
nano ~/.zshrc
```

**Add Configuration Line:** Scroll down until you find an empty area or the end of the .zshrc file. Add the following line to add Homebrew to PATH:
```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```
**Save Changes:** After you've added the line, press Ctrl + O to save changes, then press Enter. Then press Ctrl + X to exit the nano editor.

**Reload .zshrc:** To apply changes to the current terminal session, run the following command in Terminal:
```bash
source ~/.zshrc
```

Install Protocol Buffers Compiler (protoc): Protocol Buffers (protobuf) are used to define the structure of your gRPC messages and services. You need to install the protoc compiler to generate Go code from your .proto files. You can install it using Homebrew:
```bash
brew install protobuf
```

Installation Verification: After the installation is complete, you can verify the installation of protobuf by running the command:
```bash
protoc --version
```

Add to PATH: If you need to add your Homebrew bin directory to your PATH, you can add it to your .zshrc or .zprofile file as described above. Add the following line at the end of the file:
```bash
export PATH=$PATH:/opt/homebrew/bin
```

### go plugin for the protocol compiler

Install the protocol compiler plugins for Go using the following commands:
```bash
go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2
```

Update your PATH so that the protoc compiler can find the plugins:
```bash
export PATH="$PATH:$(go env GOPATH)/bin"
```