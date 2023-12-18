---
type: nav
prev: ["Documentation", "index.html"]
---


# Writing Documents

Supermark documents are simple textfiles that include chunks of text, which can use different text-based syntax like Markdown, YAML, HTML or Wikimedia tables.

* Place your source files in a folder called `pages` or sub-folders within it.
* Use the extension `*.md`.
* Use UTF-8 encoding.


## Chunks

Chunks are separated by two or more blank lines.


## Markdown Chunks

The Markdown chunks of the document should follow [Pandoc's Markdown syntax](https://pandoc.org/MANUAL.html#pandocs-markdown).
They are useful to markup paragraphs of text, headers, links and lists.


## HTML Chunks

HTML chunks are separated by other chunks with two blank lines. Just make sure there are no blank lines with the HTML code.

## Referenced Chunks

Use a chunk as a reference to other chunks defined in other files.

```yaml
---
ref: file.md
---
```

## YAML Chunks

YAML elements start and stop with a delimiter `---`.
The content must be [valid YAML syntax](https://yaml.org). 
Ths is easiest when copying existing examples. 

The detailed elements in YAML chunk are defined by extensions, explained below.


## Code Chunks

Supermark  uses Pandoc's functions to highlight code. Place the code between the following delimiters:


<div>
<pre>
```bash
pandoc --list-highlight-languages
```
</pre>
</div>


`abc`, `asn1`, `asp`, `ats`, `awk`, `actionscript`, `ada`, `agda`, `alertindent`, `apache`, `bash`, `bibtex`, `boo`, `c`, `cs`, `cpp`, `cmake`, `css`, `changelog`, `clojure`, `coffee`, `coldfusion`, `commonlisp`, `curry`, `d`, `dtd`, `diff`, `djangotemplate`, `dockerfile`, `doxygen`, `doxygenlua`, `eiffel`, `elixir`, `email`, `erlang`, `fsharp`, `fortran`, `gcc`, `glsl`, `gnuassembler`, `m4`, `go`, `html`, `hamlet`, `haskell`, `haxe`, `ini`, `isocpp`, `idris`, `fasm`, `nasm`, `json`, `jsp`, `java`, `javascript`, `javadoc`, `julia`, `kotlin`, `llvm`, `latex`, `lex`, `lilypond`, `literatecurry`, `literatehaskell`, `lua`, `mips`, `makefile`, `markdown`, `mathematica`, `matlab`, `maxima`, `mediawiki`, `metafont`, `modelines`, `modula2`, `modula3`, `monobasic`, `ocaml`, `objectivec`, `objectivecpp`, `octave`, `opencl`, `php`, `povray`, `pascal`, `perl`, `pike`, `postscript`, `powershell`, `prolog`, `pure`, `purebasic`, `python`, `r`, `relaxng`, `relaxngcompact`, `roff`, `ruby`, `rhtml`, `rust`, `sgml`, `sql`, `sqlmysql`, `sqlpostgresql`, `scala`, `scheme`, `tcl`, `tcsh`, `texinfo`, `mandoc`, `vhdl`, `verilog`, `xml`, `xul`, `yaml`, `yacc`, `zsh`, `dot`, `noweb`, `rest`, `sci`, `sed`, `xorg`, `xslt`,

For an updated list, type:

```bash
pandoc --list-highlight-languages
```

# Margin Notes


You can place the content of a chunk as additional information to another chunk. 
Margin notes are aligned to the top of the chunk they are attached to.

To start a new margin note, create a markdown chunk with a tag `:aside:` in the beginning.

:aside: This is a note at the margin. It can also contain **Markdown syntax**, and even span over several paragraphs. 

See, here is a second paragraph.





# Extensions

Supermark uses extenions to add more elements. Have a look at [all installed extenions](extenions.html).


## Paragraph Extenions

Markdown chunks can be extended with a prefix between two colons, like this:

```markdown
:warning: This is a warning box, using **Markdown** syntax inside.
```

This results in the following box:

:warning: This is a warning box, using **Markdown** syntax inside.


The `:extension:` prefix only applies to the current chunk. This means that you use **two blank lines** before you start the next chunk that is not a warning anymore.


# Constants

You can use constants in markdown chunks that are replaced during the building process.
Refer to the constant names wrapped in double curly braces and colons as shown below.

Usage of the variable in a Markdown chunk:

```markdown
This document is written in the year {{:year:}}.
```


The constants and their values are declared in the configuration file `config.toml`. 

**config.toml**
```
input = "pages"
output = "docs"

[replacements]
"year" = "2023"
```


