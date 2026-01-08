# Fuel PHP Binaries

Custom PHP binaries for [Fuel](https://github.com/ashleyhindle/fuel) - the AI agent task management CLI.

This is a fork of [phpacker/php-bin](https://github.com/phpacker/php-bin) with a customized extension list including `pcntl` and `posix` for signal handling in TUI applications.

## Extensions

Compiled extensions (see [php-extensions.txt](php-extensions.txt)):

```
bcmath, ctype, curl, dom, fileinfo, filter, iconv, mbstring, openssl,
pcntl, phar, posix, simplexml, tokenizer, xml, xmlreader, xmlwriter, zlib
```

## Platforms

- macOS arm64 (Apple Silicon)
- macOS x64 (Intel)
- Linux arm64
- Linux x64

## PHP Version

Currently builds PHP 8.4 only.

## Usage

Used automatically by [Fuel](https://github.com/ashleyhindle/fuel) via phpacker:

```bash
phpacker build --repository="ashleyhindle/fuel-php-bin" ...
```

## Building

Binaries are built using [static-php-cli](https://static-php.dev) via GitHub Actions. The workflow runs weekly or can be triggered manually.

## Credits

- [phpacker/php-bin](https://github.com/phpacker/php-bin) - Original project
- [NativePHP/php-bin](https://github.com/NativePHP/php-bin) - Upstream
- [static-php-cli](https://github.com/crazywhalecc/static-php-cli) - Build tool

## License

This repository is a redistribution of PHP. See [license-files/](license-files/) for applicable licenses.
