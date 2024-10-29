# tdl Extension Template

## Introduction

This template provides instructions on how to use the tdl extension template. 
The template helps you create, build, and publish extensions for the tdl.

> [!WARNING]
> tdl Extensions are in the beta stage. The API may change in the future.

## Prerequisites

- `Go` programming language installed (version 1.21 or higher)
- `Git` installed
- `tdl` command-line tool installed

## Getting Started

1. **Create a New Repository**

   Click on the "Use this template" button to create a new repository based on this template.

   > Note: repository name should be in the format `tdl-<extension-name>`

2. **Clone the Repository**

   Clone the template repository to your local machine:

   ```sh
   git clone https://github.com/<username>/<repository>.git
   cd <repository>
   ```

3. **Update the go.mod File**

   Update the `go.mod` file with the correct module name:

   ```sh
   module github.com/<username>/<repository>
   ```

4. **Install Dependencies**

   Navigate to the project directory and install the required dependencies:

   ```sh
   go mod tidy
   ```

## Build

To build the extension, run the following command:

```sh
go build
```

This will create an executable in the project directory.

## Test

To test the extension, run the following commands:

```sh
tdl extension install --force ./tdl-extension
```

```sh
tdl <global-config-flags> <extension-name> <extension-flags>
```

This will install the extension in the tdl extension directory as `local` extension.

## Publish

To publish your extension, follow these steps:

1. **Create a New Tag**
    
    Create a new semver tag and push it to the repository:

    ```sh
    git tag v0.1.0
    git push origin v0.1.0
    ```

2. **Wait for the GitHub Action to Complete**

    The GitHub Action `release` will build and publish the extension to a new release.

3. **Edit the draft release**

    Edit the draft release and publish it.
