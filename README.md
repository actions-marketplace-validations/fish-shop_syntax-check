# fish-shop/syntax-check

[![Tests Status](https://github.com/fish-shop/syntax-check/actions/workflows/test.yml/badge.svg)](https://github.com/fish-shop/syntax-check/actions?query=workflow%3Atests) [![License](https://img.shields.io/badge/license-MIT-blue)](http://opensource.org/licenses/mit-license.php) [![fish](https://img.shields.io/badge/fish-3.2.2-blue)](https://fishshell.com) [![Issues](https://img.shields.io/github/issues/fish-shop/syntax-check)](https://github.com/fish-shop/syntax-check/issues)

A GitHub action for syntax checking [fish shell](https://fishshell.com) files.

<img src="example.png">

## Prerequisites

This action requires the [fish shell](https://fishshell.com). You can install it using the [fish-actions/install-fish](https://github.com/fish-actions/install-fish) action.

## Usage

Add a suitable `uses` step to your GitHub [workflow](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions) as shown below:

```yaml
- name: Syntax check
  uses: fish-shop/syntax-check@v1
```

By default, all files under `$GITHUB_WORKSPACE` with a `.fish` file extension are checked. To specify a different file pattern to match against, provide a value for the `pattern` input. For example, to check all `.fish` files starting in the `src` directory and descending into subdirectories:

```yaml
- name: Syntax check
  uses: fish-shop/syntax-check@v1
  with:
    pattern: src/**.fish
```

Multiple space-separated `pattern` values are supported and can include [wildcards](http://fishshell.com/docs/current/index.html#wildcards-globbing) and [brace expansion](http://fishshell.com/docs/current/index.html#brace-expansion):

```yaml
- name: Syntax check
  uses: fish-shop/syntax-check@v1
  with:
    pattern: init.fish functions/**.fish {conf.d,completions}/**.fish tests/???-*.fish
```

## Action versions

Use one of the following patterns when specifying the version reference for this action in your workflow (i.e. the `{ref}` value in `uses: fish-shop/syntax-check@{ref}`):

| Pattern  | Example   | Description                                                            |
|----------|-----------|------------------------------------------------------------------------|
| `vX`     | `v1`      | the latest `v1.*` release including non-breaking changes and bug fixes |
| `vX.Y`   | `v1.1`    | the latest `v1.1.*` release including bug fixes                        |
| `vX.Y.Z` | `v1.1.0`  | the `v1.1.0` release only                                      |                

The recommended pattern is `vX` (e.g. `v1`). This will ensure that the version of the action used in your workflow includes the latest non-breaking changes and bug fixes, and guarantees compatibility with previous versions of that major release number.

Using a `main` branch reference in your workflow is _not_ recommended as this branch may include breaking changes intended for the next major release.

## Acknowledgements

* This project was inspired by [fish-actions/syntax-check](https://github.com/fish-actions/syntax-check).

## License
`fish-shop/syntax-check` is provided under the terms of the [MIT License](http://opensource.org/licenses/mit-license.php).

## Contact
Email me at [marc.ransome@fidgetbox.co.uk](mailto:marc.ransome@fidgetbox.co.uk) or tweet [@marcransome](http://www.twitter.com/marcransome).
