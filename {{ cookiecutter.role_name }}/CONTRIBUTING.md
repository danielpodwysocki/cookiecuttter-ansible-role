## Development workflow

This repository relies on Molecule for testing and development.
It uses the Vagrant driver - you will need to have Vagrant installed and set up with the
viirtualbox provider.

## Generating the README.md

The README.md shouldn't be edited directly. Instead, edit the README.md.j2 template and run
`make readme` to generate the README.md.

The template resides in the docs/readme directory.

### Documenting variables
Each variable should have an explicit default value in defaults/main.yml.

Above the var, document it with a comment. The comment should be in the form:

```
#@var <variable name>:description: This is my description
<variable name>: <default value>
```

## Makefile targets & molecule commands

```
make lint