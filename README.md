# txt2nato

A command-line utility that converts text into the [NATO phonetic alphabet](https://en.wikipedia.org/wiki/NATO_phonetic_alphabet). Useful for spelling out passwords, codes, or any text over the phone or radio where clarity matters.

## Features

- Converts letters, numbers, and common symbols to NATO phonetic equivalents
- Automatically prefixes uppercase letters and digits for clarity (e.g. `Uppercase Alpha`, `Number Three`)
- Falls back to the raw character for any unrecognized input
- Three output modes: default, password, and inline
- Interactive mode when no text argument is provided

## Requirements

- Python 3.9+
- No external dependencies

## Usage

```
nato [-h] [-p] [-i] [text ...]
```

### Arguments

| Argument | Description |
|---|---|
| `text` | Text to convert. If omitted, prompts interactively. |
| `-p`, `--password` | Format output for password dictation (shows original + indented phonetics) |
| `-i`, `--inline` | Output all phonetics on one line, comma-separated |
| `-h`, `--help` | Show help message and exit |

## Examples

### Default output — one phonetic word per line

```
$ ./nato.py Hello
Uppercase Hotel
Echo
Lima
Lima
Oscar
```

### Password mode — shows original password alongside phonetics

```
$ ./nato.py -p MyP@ss123

Your password: MyP@ss123

	Uppercase Mike
	Yankee
	Uppercase Papa
	At Symbol
	Sierra
	Sierra
	Number One
	Number Two
	Number Three
```

### Inline mode — comma-separated on a single line

```
$ ./nato.py -i Hello
Uppercase Hotel, Echo, Lima, Lima, Oscar
```

### Interactive mode — prompts for input when no text is provided

```
$ ./nato.py
Please enter text to convert: Hi
Uppercase Hotel
India
```

### Multi-word input

```
$ ./nato.py say again
Sierra
Alpha
Yankee
Space
Alpha
Golf
Alpha
India
November
```

## Supported Characters

| Category | Characters |
|---|---|
| Letters | A–Z (with uppercase detection) |
| Numbers | 0–9 (prefixed with "Number") |
| Symbols | `! @ # $ % ^ & * ( ) _ - + = { } [ ] \| \ : ; " ' < > , . ? /` |
| Whitespace | Space → `Space` |

## License

MIT
