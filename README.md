# org-labels [![NPM Version](https://badge.fury.io/js/org-labels.svg)](https://badge.fury.io/js/org-labels)

A tool to help manage organization-wide GitHub issue labels.

### Install

```sh
$ npm install -g org-labels
```

## Usage

Requires node.js 0.11+ - use a node version manager [such as __n__](https://www.npmjs.org/package/n) to switch versions easily.

Requires a GITHUB_API_TOKEN environment variable. - use [set-env](https://www.npmjs.org/package/set-env) to easily set it. This token must be a [GitHub Personal API Token](https://github.com/blog/1509-personal-api-tokens). It must have either `repo` or at least `public_repo` access.

```sh
$ sudo n 0.11.13

$ org-labels <command>
```

### Commands

- `add` `<org> <label> <color>` - adds a label to all repos.
- `remove` `<org> <label>` - removes a label from all repos.
- `update` `<org> <label> <color>` - updates an existing label for all repos.
- `rename` `<org> <label> <new>` - renames an existing label for all repos.
- `standardize` `<org> <repo>` - reads a `config/github_labels.json` file from a repo and adds / updates labels on all repos.

__color__ must be a hexadecimal color code without the preceding `#`.

#### Options

- `-d` `--destructive` - When enabled, allows `standardize` to remove labels not found in the config file.

### Example

The following would add a `docs` issue label with the color `d4c5f9` to every repo in `repo-utils`.

```sh
$ org-labels add repo-utils docs d4c5f9
```

## License

The MIT License (MIT)

Copyright (c) 2014 Jeremiah "Fishrock123" Senkpiel fishrock123@rocketmail.com

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
