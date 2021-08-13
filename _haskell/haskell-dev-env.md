---
layout: default
title: Haskell Development Environment
description: CSCI 335  - Functional Programming
---

# Installing a Basic Haskell Development Environment

## Installing Haskell Binaries

- Navigate to [https://www.haskell.org/ghcup/](https://www.haskell.org/ghcup/)
- Copy the Terminal command displayed 
  - The displayed command changes based on OS used to access the page.
- (Windows) Execute the command in Powershell ([IMAGE](./assets/img/PSInstallGcup.png))
    - Accept the default answers to the questions that come up:
      - `Mys2` toolchain should be installed.
      - `Haskell Language Server` should not be installed.
      - `Stack` should not be installed.
- (*nix) Execute the command in Terminal ([IMAGE](./assets/img/NexChcupCmd.png))
    - If the required Build tools are not already installed, the command will not work.
    - (Mac) The command will trigger install of Build tools, which should be installed. The command will then need to be re-run.
    - (Linux) The tools `curl gcc make` need to be installed prior to running the `ghcup` installation command. ([IMAGE](./assets/img/NixTerminalInstallCurlMakeGcc.png))
    - `Haskell Language Server` should not be installed. ([IMAGE](./assets/img/NixGhcupQuestions.png))
    - `Stack` should not be installed. ([IMAGE](./assets/img/NixGhcupQuestions.png))
- **Pay attention to where the Haskell files are being installed!**

## Checking Binary Installation

- Close and restart Powershell or Terminal
- Execute the following commands: ([IMAGE](./assets/img/PSCheckingInstall.png))
  - Type and execute `ghc --version`.
  - Type and execute `cabal --version`.
  - Type and execute `ghci`.
    - Try executing arithmetic in `ghci` (i.e. type `2 + 3` at the `ghci` prompt).
    - Type `:quit` at the `ghci` prompt to exit `ghci`.
- If the preceding commands functioned, skip to the next section
- If the preceding commands did not function and `ghcup` succesfully installed, the binaries will have to be added to the PATH

## Installing Visual Studio Code

- Navigate to [https://code.visualstudio.com/download](https://code.visualstudio.com/download)
- Download and install the appropriate VSCode package ([IMAGE](./assets/img/DownloadVSCode.png))
- Start Visual Studio Code

## Installing VSCode Extensions

- Go to the 'Extensions' view of VSCode
  - Please see [https://code.visualstudio.com/docs/editor/extension-marketplace](https://code.visualstudio.com/docs/editor/extension-marketplace) if there are questions about VSCode extension management.
- Search for 'Haskell Syntax Highlighting' and Install this extension ([IMAGE](./assets/img/InstallSyntaxHighlighting.png))
- Search for 'Code Runner' and Install this extension ([IMAGE](./assets/img/InstallCodeRunnerVSCode.png))

## The Final Checks

- Create a new file in VSCode (File -> 'New File') and save it as `test.hs`
- Type:

```haskell
module Test where

main :: IO ()
main = putStrLn "Hello World"
```

- Right Click/Context Click and select 'Run Code'
- A Terminal should appear within VSCode and execute the `test.hs` file with a return of "Hello World"

# Notes

- The Terminal in VSCode is the same as any other system Terminal and can run `ghc`, `cabal`, or `ghci`
  - The VSCode Terminal can be accessed through View -> 'Terminal' or Terminal -> 'New Terminal'. ([IMAGE](./assets/img/VSCodeAccessTerminal.png))
  - The default location for a new VSCode terminal is the Open Folder or the 'Home' folder if no folder is open in VSCode.

## Optional

- The `Haskell` extension for VSCode provides a more IDE-like experience for Haskell development
  - Not required for the Functional Programming course.
  - The extension will download `Haskell Language Server` which is required for it to function.
  - At the time of writing, the version of `ghc` needs to be < 9.0.0 for `Haskell Language Server` to work.
  - I had a lot of problems getting this to work on Ubuntu Linux, so may not work for everyone.
- The `haskell-linter` extension for VSCode provides guidance on how to properly format Haskell files
  - The extension requires the `hlint` Haskell package to be installed.
  - `hlint` can be installed through the `cabal` command.
  - The `hlint` binary may have to be manually added to the PATH for the extension to use it.
