# PHP 8.4 WebAssembly (WASI) for Wasmer

This repository contains an automated build system using GitHub Actions to compile PHP 8.4 into WebAssembly (WASI) format so it can run within the Wasmer ecosystem.

## How It Works

Every time you push to the `main` branch, GitHub Actions will:
1. Run an `ubuntu-latest` runner.
2. Download **WASI SDK 20.0**.
3. Fetch the latest raw source code of PHP (version 8.4 / `master` branch).
4. Compile it into a `php.wasm` file.
5. Automatically publish it to the [Wasmer Registry](https://wasmer.io/) using the credentials set in Secrets.

## Requirements
For the publish step to Wasmer to run automatically, make sure you go to **Settings > Secrets and variables > Actions** in this GitHub repository, and add a new secret named:
- `WASMER_TOKEN` (Fill it with your Wasmer API Token).
