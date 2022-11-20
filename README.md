Forked from https://github.com/kevb34ns/auto-comment-blocks

Download .VSIX file to install: https://github.com/brianbuie/auto-comment-blocks/blob/master/auto-comment-blocks-1.0.2.vsix

---

# Auto Comment Blocks

Provides block comment completion for Javadoc-style multi-line comments and single-line comment blocks for most officially supported languages.

## Usage
![Demo](https://raw.githubusercontent.com/brianbuie/auto-comment-blocks/master/img/demo.gif)

### Javadoc-style comment blocks
Type `/**` to start a block comment, then hit the Enter key, and the extension will close the block. While inside the comment block, the extension will insert an asterisk at the start of every new line, and align the comment, respecting indentation.

### QDoc-style (Qt) comment blocks
Use `/*!` in C/C++ files to start a QDoc comment block.

### "single-line" block comments
You can insert single line comment blocks for languages with `//`, `#`, or `;` style single line comments. Press `Shift+Enter` while on a commented line to insert a new commented line with the same level of indentation. See the Settings section for issues and more options.

### Language Support

| Comment Style | Language Support |
| ------- | ------- |
| `/** */` | C, C++, C#, CSS, Go, Groovy, Java, Javascript, Less, Objective C/C++, PHP, Sass, Rust, Swift, Typescript |
| `/*! */` | C, C++ |
| `//`, `///` | C, C++, C#, F#, Go, Groovy, Java, JavaScript, Less, Objective C/C++, PHP, Rust, Sass, Swift, TypeScript |
| `#` | CoffeeScript, Dockerfile, Makefile, Perl, PowerShell, Python, R, Ruby, YAML |
| `;` | Clojure |

## Settings

Reload the extension after changing any settings.

* `auto-comment-blocks.singleLineBlockOnEnter`: If enabled, pressing `Enter` inserts a new commented line at the same indentation, and pressing `Shift+Enter` breaks the comment block.
  + **Caution**: This feature is buggy in many languages (see Issues section), but it seems to work fine for C, C++, Go, Less, PHP, Ruby, and Sass.
* `auto-comment-blocks.disabledLanguages`: Add languageIds here to disable any comment completion for that language.
* `auto-comment-blocks.slashStyleBlocks`: Add languageIds here to enable '//' and '///'-style single line comment blocks for that language.
* `auto-comment-blocks.hashStyleBlocks`: Add languageIds here to enable '#'-style single line comment blocks for that language.
* `auto-comment-blocks.semicolonStyleBlocks`: Add languageIds here to enable ';'-style single line comment blocks for that language.

## Issues

* Single-line blocks using `Enter`: if you enable the `singleLineBlockOnEnter` setting, there are a few things to keep in mind:
  + It seems to work find for C, C++, Go, Less, PHP, Ruby, and Sass.
  + It doesn't work at all for Python, JavaScript, and TypeScript.
  + For every other language, if you press `Tab` immediately after breaking out of a comment block, it will insert a commented line, for some unknown reason.
* Sometimes multi-line completion/aseterisk insertion doesn't work. The reason is still unknown. It may go away if you reload your workspace.
* Currently, VS Code only allows extensions to overwrite, instead of modify, existing language configurations. This means that this extension may clash with another extension that overwrites the same language configurations, causing one or both not to work. In that case, uninstalling this extension is the only option for now.

## Release Notes

#### 1.0.2 (this fork)
- Add multi-line support for Javascript and Typescript
- Add compiled .vsix file to download/install instead of publishing to VSCode marketplace

#### 1.0.1 ([original repo](https://github.com/kevb34ns/auto-comment-blocks))
- Add multi-line support for Rust, Go
- Add single-line support for YAML

#### 1.0.0
- Add multi-line comment support for Less, Objective-C/C++, and Swift.
- Add single-line comment blocks for most officially supported languages. See README for more information.
