# Documenting

The Vector team loves its documentation and if you help write it then it loves
you too.

## The Basics

1. Vector's documentation is located in the [website/docs](./website/docs)
   folder.
2. If a file contains an "AUTOGENERATED" warning at the top, do not modify the
   file directly. Instead modify the referenced template.
3. Reference documents ([website/docs/reference](./website/docs/reference))
   are generated automatically using specs found in [.meta](./.meta).
4. Run `make generate` to re-generate files.

### Component Documentation

The bulk of documentation for sources, transforms and sinks is generated from a
single specification, written in TOML, and found within [.meta](./.meta).

Since component additions and changes are the majority of contributions made to
the Vector project it is most likely that you'll need to edit these files when
updating documentation.

If you are adding an entirely new component then you will need to create both a
spec within [.meta](./.meta) and a template within
[website/docs/reference](./website/docs/reference). For example, if we were to
create a hypothetical new sink called `foo` then to get us started we could
create copies of these files from the `blackhole` sink:

```sh
cp ./.meta/sinks/blackhole.toml ./.meta/sinks/foo.toml
cp ./website/docs/reference/sinks/blackhole.md.rb ./website/docs/reference/sinks/foo.md.rb
```

And then we would edit those new files and generate the final documents with
`make generate`.

## Advanced

### Website

The documentation site is built using [Docusaurus](https://docusaurus.io/) and
can be found in the [website](./website) folder. You can read more about how it
works and how to run it locally in [the README](./website/README.md).


### Scripting

Vector documentation is mostly generated using Ruby, where the scripts can be
found within the [scripts](./scripts) folder. You can read more about these
scripts in [the README](./scripts/README.md).
