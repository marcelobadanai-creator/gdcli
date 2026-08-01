# Google Drive CLI (gdcli)

`gdcli` is a lightweight, command-line interface tool designed to interact with Google Drive. It allows you to manage configurations, authenticate, upload/download files and folders, handle streams via `stdin`/`stdout`, and manage remote items efficiently.


## Google OAuth Configuration

`gdcli` requires a Google OAuth Client configuration.

For security reasons, OAuth credentials are not included with the binary distribution.

Before using `gdcli`, create your own OAuth client in Google Cloud Console and configure:

- project_id
- client_id
- client_secret

See:

docs/google-oauth-setup.md


---

## Table of Contents
1. [Installation & Building](#installation--building)
2. [Usage Overview](#usage-overview)
3. [Subcommands Reference](#subcommands-reference)
   * [`define`](#define)
   * [`login`](#login)
   * [`ls`](#ls)
   * [`upload`](#upload)
   * [`download`](#download)
   * [`rm`](#rm)
   * [`to`](#to)
   * [`from`](#from)
   * [`mkdir`](#mkdir)
   * [`rename`](#rename)

---

## Installation & Building

Make sure you have the required dependencies (such as [CLI11](https://github.com/CLIUtils/CLI11)) installed in your project, then compile your source files including `gdcli`.

---

## Usage Overview

```bash
gdcli [subcommand] [options] [arguments]

To view the general help menu or help for any specific subcommand, use:
```bash
gdcli --help
gdcli <subcommand> --help

---

## Subcommands Reference

### `define`
Define configurations and save them.

* **Options:**
  * `--dp`, `--data-path <path>` — Set the data path (models directory).

---

### `login`
Authenticate with Google Drive.

* *No additional options required.*

---

### `ls`
List files and folders in Google Drive.

* **Arguments:**
  * `remote_path` — Remote path, type `"/"` for root.

---

### `upload`
Upload local files or folders to Google Drive.

* **Arguments:**
  * `local_path` *(Required)* — Local path for files or folders. For folders, use the `--recursive` flag.
  * `remote_path` *(Required)* — Remote path, type `"/"` for root.
* **Flags:**
  * `-o`, `--override` — Force overwrite if the remote file or folder already exists.
  * `-r`, `--recursive` — Enable recursive operation (for folder mode).

---

### `download`
Download files or folders from Google Drive to a local path.

* **Arguments:**
  * `local_path` — Local path for files or folders.
  * `remote_path` — Remote path, type `"/"` for root folder. For folders, use the `--recursive` flag.
* **Flags:**
  * `-o`, `--override` — Force overwrite if the local file or folder already exists.
  * `-r`, `--recursive` — Enable recursive operation (for folder mode).

---

### `rm`
Remove an item from Google Drive.

* **Arguments:**
  * `remote_path` *(Required)* — Remote path for a file or folder. Root `"/"` is not allowed.

---

### `to`
Upload files to Google Drive via `stdin` or a dump file (useful for streams and advanced pipelines).

* **Arguments:**
  * `remote_path` *(Required)* — Remote path, type `"/"` for root.
* **Flags:**
  * `--dump-file` — Use upload preview dump files (does not use `stdin`).
  * `-o`, `--override` — Force overwrite if the remote file already exists.
  * `--as`, `--allocation-size <size>` — Allocation size (memory page in deque), default: `64mb`.
  * `--mm`, `--max-mem-size <size>` — Maximum memory for buffering, default: do not use, write to dummy file.
  * `--ss`, `--split-size <size>` — Split file into parts, usage: `--ss 100mb`.
  * `--df`, `--dummy-file <path>` — Dummy file to receive `stdin` (Google Drive requires total file size for resumable uploads), default: `/tmp/gdcli.tmp`.
  * `-s`, `--shrink` — Shrink memory allocation after upload (by segment), default: `true`.
  * `--olm`, `--online-mode <ON|OFF>` — Configure online operation: `"ON"` to use online features (default) or `"OFF"` to turn off cloud sync (for offline-only use).
  * `--ofm`, `--offline-mode <ON|OFF|TURN>` — Configure offline operation: `"MIRROR"` to also dump to a file, `"OFF"` to disable local writes, or `"TURN"` (default) to enable offline fallback if online upload fails.
  * `--op`, `--offline-path <path>` — Define the offline target path.

---

### `from`
Download files from Google Drive directly to `stdout`.

* **Arguments:**
  * `remote_path` *(Required)* — Remote path for regular files (folders are not allowed).
* **Flags:**
  * `-q`, `--quiet` — Hide progress information to output raw bytes only, default: `true`. Useful when programs cannot distinguish `std::cerr` (progress) from `std::cout` (data).
  * `--mf`, `--mult-files` — Dump all files starting with the remote path (useful for partial files). Files are downloaded in alphabetical order.

---

### `mkdir`
Create a folder on Google Drive.

* **Arguments:**
  * `remote_path` *(Required)* — Remote path of the folder to be created.
* **Flags:**
  * `-p`, `--progressive` — Create multiple folders and subfolders recursively, default: `false`.

---

### `rename`
Rename a file or folder on Google Drive.

* **Arguments:**
  * `remote_path` *(Required)* — Remote path of the file or folder to be renamed.
  * `new_name` *(Required)* — New name for the item.