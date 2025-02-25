# Cheatsheet CLI

`cheatsheet` is a command-line tool written in Rust that lets users quickly view cheat sheets on the command line. Use markdown to create and modify the default or create new cheat sheets. 

## Table of Contents

- [Cheatsheet CLI](#cheatsheet-cli)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
    - [Homebrew (MacOS)](#homebrew-macos)
    - [Cargo](#cargo)
  - [Usage](#usage)
  - [Available Cheatsheets](#available-cheatsheets)
  - [Create a new cheatsheet](#create-a-new-cheatsheet)
  - [Troubleshooting](#troubleshooting)



## Installation

### Homebrew (MacOS)
```sh
  brew tap jheryer/tap
  brew install cheatsheetrs 
```

### Cargo

To install `cheatsheet`, ensure you have [Rust and Cargo installed](https://www.rust-lang.org/tools/install) on your system. Then, follow these steps:

1. Clone the repository:

```sh
git clone git@github.com:jheryer/cheatsheetrs.git
```

2. Change to the cheatsheet directory:
```sh
cd cheatsheetrs
```
3. Build and Install
```sh
cargo build --release
cargo install --path .
cp -r sheets ~/.cheatsheets
export CHEAT_SHEET_PATH=~/.cheatsheets
```
4. (Optional) Configure CLI to permanently set environment variable for cheatsheet
```sh
echo -e "\nexport CHEAT_SHEET_PATH=~/.cheatsheets" >> ~/.zshrc
```
5. (Optional) Create an alias
```sh
echo -e "\nalias cs='cheatsheet'" >> ~/.zshrc
. ~/.zshrc
cs --list
```

## Usage
* List all cheat sheets
  ```sh
  cheatsheet --list
  ```
* Show the docker cheat sheet
  ```sh
  cheatsheet docker
  ```
* Show the sections in the docker cheat sheet
  ```sh
  cheatsheet docker -l
  ```
* Show only the general and images sections in the docker cheat sheet
  ```sh
  cheatsheet docker general images
  ``` 
* Show help
  ```sh
  cheatsheet --help
  ``` 


## Available Cheatsheets
* markdown
* vim
* gsutil
* k8s
* maven
* terraform
* git
* docker
* aws
* gcloud
* xcodebuild
* conda
* sed
* cargo

## Create a new cheatsheet
Create a new markdown file in $CHEAT_SHEET_PATH and verify it shows up with --list. Markdown headings provide filtering by section.


## Troubleshooting
```sh
cheatsheet --list
No such file or directory (os error 2)
```
Ensure the $CHEAT_SHEET_PATH is set
```sh
export CHEAT_SHEET_PATH=~/.cheatsheets
```
