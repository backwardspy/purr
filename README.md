# uu

Utility commands for managing userstyles. Query data about the repository, the userstyles, and the maintainers, or initialize a new userstyle from the template.

## Installation

```sh
cargo install uu
```

## Usage

```
Usage: uu <COMMAND>

Commands:
  query
  init
  help   Print this message or the help of the given subcommand(s)

Options:
  -h, --help     Print help
  -V, --version  Print version
```

### `query`

All of the query commands can be used with the `-o`/`--output` flag to change the output format between JSON and plain.

```
Usage: uu query [OPTIONS] [COMMAND]

Commands:
  maintained
  help        Print this message or the help of the given subcommand(s)

Options:
  -c, --count
  -o, --output <FORMAT>  [default: json] [possible values: json, plain]
  -h, --help             Print help
```

**Examples**:

- List the userstyles.

  ```
  uu query
  ```

- Count the number of userstyles.

  ```
  uu query --count
  ```

#### `maintained`

```
Usage: uu query maintained [OPTIONS]

Options:
      --by <NAME>
  -n, --not
  -c, --count
  -o, --output <FORMAT>  [default: json] [possible values: json, plain]
  -h, --help             Print help
```

**Examples**:

- List maintained userstyles.

  ```
  uu query maintained
  ```

- Count the number of maintained userstyles.

  ```
  uu query maintained --count
  ```

- List *un*maintained userstyles.

  ```
  uu query maintained --not
  ```

- Count the number of *un*maintained userstyles.

  ```
  uu query maintained --not --count
  ```

- List userstyles maintained by `<username>`.

  ```
  uu query maintained --by "<username>"
  ```

- Count the number of userstyles maintained by `<username>`.

  ```
  uu query maintained --by "<username>" --count
  ```

- List userstyles _not_ maintained by `<username>`.

  ```
  uu query maintained --by "<username>" --not
  ```

- Count the number of userstyles _not_ maintained by `<username>`.

  ```
  uu query maintained --by "<username>" --not --count
  ```

### `init`

The `init` command accepts each value (name, categories, etc.) via arguments, though if not provided a series of prompts will be displayed instead.

```
Usage: uu init [OPTIONS]

Options:
      --name <NAME>
      --category <CATEGORIES>
      --icon <ICON>
      --color <COLOR>
      --app-link <APP_LINK>
  -h, --help                   Print help
```

## License

[MIT](LICENSE)
