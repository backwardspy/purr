# purr

Query data about the Catppuccin project, the [catppuccin/userstyles](https://github.com/catppuccin/userstyles) subproject, maintainers, or even initialize a new port/userstyle from a template.

## Installation

### Cargo

```sh
cargo install --git https://github.com/uncenter/purr.git
```

### Nix

```
nix run github:uncenter/purr
```

## Usage

```
purr <COMMAND> [-h | --help] [-V | --version]
```

### `query`

```
purr query [-c | --count] [-o | --output]
```

Query the ports.yml data source. With no arguments the names of the ports are displayed.

#### `-o` / `--output`

Both query commands can be used with the `-o`/`--output` option to change the output format to either `json` and `plain` (defaults to `json`).

#### `--count`

Count the number of ports.

#### `maintained`

```
purr query maintained [--by <NAME>] [-n | --not] [-c | --count] [-o | --output]
```

**Examples**:

- List maintained ports.

  ```
  purr query maintained
  ```

- Count the number of maintained ports.

  ```
  purr query maintained --count
  ```

- List *un*maintained ports.

  ```
  purr query maintained --not
  ```

- Count the number of *un*maintained ports.

  ```
  purr query maintained --not --count
  ```

- List ports maintained by `<username>`.

  ```
  purr query maintained --by "<username>"
  ```

- Count the number of ports maintained by `<username>`.

  ```
  purr query maintained --by "<username>" --count
  ```

- List ports _not_ maintained by `<username>`.

  ```
  purr query maintained --by "<username>" --not
  ```

- Count the number of ports _not_ maintained by `<username>`.

  ```
  purr query maintained --by "<username>" --not --count
  ```

#### `has`

```
purr query has [PROPERTIES] [-n | --not] [-c | --count] [-l | --list] [-o | --output]
```

**Properties:**

- `--name <NAME>`
- `--category <CATEGORIES>`
- `--icon <ICON>`
- `--color <COLOR>`
- `--url <URL>`

**Examples**:

- Check if userstyles exist with `color` set to `mauve`.

  ```
  purr userstyles query has --color mauve
  ```

- List userstyles that have `color` set to `mauve`.

  ```
  purr userstyles query has --color mauve --list
  ```

- Count the number of userstyles that have `color` set to `mauve`.

  ```
  purr userstyles query has --color mauve --count
  ```

- Count the number of userstyles that have `color` set to anything other than `mauve`.

  ```
  purr userstyles query has --color mauve --not --count
  ```

- List userstyles that do not have `icon` defined.

  ```
  purr userstyles query has --icon --not --list
  ```

### `userstyles`

#### `query`

```
purr userstyles query [-c | --count] [-o | --output]
```

Query the userstyles.yml data source. With no arguments the names of the userstyles are displayed.

##### `-o` / `--output`

Both query commands can be used with the `-o`/`--output` option to change the output format to either `json` and `plain` (defaults to `json`).

##### `--count`

Count the number of userstyles.

##### `maintained`

```
purr userstyles query maintained [--by <NAME>] [-n | --not] [-c | --count] [-o | --output]
```

**Examples**:

- List maintained userstyles.

  ```
  purr userstyles query maintained
  ```

- Count the number of maintained userstyles.

  ```
  purr userstyles query maintained --count
  ```

- List *un*maintained userstyles.

  ```
  purr userstyles query maintained --not
  ```

- Count the number of *un*maintained userstyles.

  ```
  purr userstyles query maintained --not --count
  ```

- List userstyles maintained by `<username>`.

  ```
  purr userstyles query maintained --by "<username>"
  ```

- Count the number of userstyles maintained by `<username>`.

  ```
  purr userstyles query maintained --by "<username>" --count
  ```

- List userstyles _not_ maintained by `<username>`.

  ```
  purr userstyles query maintained --by "<username>" --not
  ```

- Count the number of userstyles _not_ maintained by `<username>`.

  ```
  purr userstyles query maintained --by "<username>" --not --count
  ```

##### `has`

```
purr userstyles query has [PROPERTIES] [-n | --not] [-c | --count] [-l | --list] [-o | --output]
```

**Properties:**

- `--name <NAME>`
- `--category <CATEGORIES>`
- `--icon <ICON>`
- `--color <COLOR>`
- `--app-link <APP_LINK>`

**Examples**:

- Check if userstyles exist with `color` set to `mauve`.

  ```
  purr userstyles query has --color mauve
  ```

- List userstyles that have `color` set to `mauve`.

  ```
  purr userstyles query has --color mauve --list
  ```

- Count the number of userstyles that have `color` set to `mauve`.

  ```
  purr userstyles query has --color mauve --count
  ```

- Count the number of userstyles that have `color` set to anything other than `mauve`.

  ```
  purr userstyles query has --color mauve --not --count
  ```

- List userstyles that do not have `icon` defined.

  ```
  purr userstyles query has --icon --not --list
  ```

#### `init`

The `init` command accepts each value (name, categories, etc.) via arguments, though if not provided a series of prompts will be displayed instead.

```
purr userstyles init [PROPERTIES]
```

**Properties**:

- `--name <NAME>`
- `--category <CATEGORIES>`
- `--icon <ICON>`
- `--color <COLOR>`
- `--app-link <APP_LINK>`

## Roadmap

- [ ] Query GitHub stars
- [ ] Query contributors
- [ ] Query maintainers
- [ ] Query PRs (per userstyle, dated/at what time, by who)
- [ ] Init https://github.com/catppuccin/template

## License

[MIT](LICENSE)
