---
type: nav
prev: ["Documentation", "index.html"]
---

# Usage


## Default Directory Structure

:tree:
- site/
    - pages/
        - index.md
        - hello.md
        - unit-1/
            figures/
            index.md
            preparation.md
    - templates/
        - page.html
    - docs/
        - assets/
           - index.html
           - hello.html
        - unit-1/
            - figures/
            - ...
        - index.html
        - hello.html
    - config.toml

The config.toml file contains a configuration.

```toml
input = "pages"
output = "docs"

[replacements]
"year" = "2023"
```



## Default Command

Move into the main folder of your project, and run the following command:

```
supermark build
````

Supermark will look for *.md files in the `pages` folder and transform each of them into a html file placed at in the docs foler.


## Most Common Options

- `--all`, `-a` --- re-generate *all* files, not only the ones changed.
- `--verbose`, `-v` --- tell more about what the program does.

## Additional Options

- `--draft`, `-d` --- also print draft parts of the documents.
- `--input`, `-i` --- input directory containing the *.md files.
- `--output`, `-o` --- output directory.
- `--template`, `-t` --- template file for the transformation.