# eberban

__Eberban__ is a [logical] [constructed language] aimed to satisfy the
following goals :

- __being simple :__ the Eberban grammar allows manipulating predicates with
  particles in a way that is close to the [higher-order logic] it
  translates into, while abstracting away the verbosity of explicitely
  providing variables as arguments of predicates.
- __being regular :__ valid sentences are syntaxicaly unambiguous. Most grammar
  rules rely on particles which are organised in families, each starting with
  a unique prefix. Many additional patterns are shared between particles and
  predicate words to help learning groups of related words.
- __being expressive :__ the grammar and core vocabulary focus on providing a
  simple framework, on top of which can be built abstractions, complex concepts
  and tools. Since those are built into Eberban itself, users can create their
  own tools and abstractions to express entirely new concepts.

__Eberban__ take inspirations from [Lojban] and other logical languages, but try
novel approaches to satisfy the above goals.

Most resources are hosted on [GitHub pages], such as :

- parsers, which transform text into a tree structure, that can also be
  visualized as nested boxes.
- a dictionnary allowing to search words and their definitions.
- learning resources to discover the language grammar and concepts.

If you would like to get involved, please also consider joining our
[Discord server].

[Lojban]: https://mw.lojban.org/papri/Lojban
[logical]: https://en.wikipedia.org/wiki/Engineered_language#Logical_languages
[constructed language]: https://en.wikipedia.org/wiki/Constructed_language
[higher-order logic]: https://en.wikipedia.org/wiki/Higher-order_logic
[GitHub pages]: https://eberban.github.io/eberban/
[Discord server]: https://discord.com/invite/KKB79RwWUc

-----

## How to update the parser and dictionary

To build the dictionary and parser locally, you must have NodeJS and NPM
[installed](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm).
Open a terminal in the `node` folder and run once the following command:

```
npm i
```

After every change in the `node` folder or in the dictionary, run the following command to build:

```
npm run build
```

To open the web pages in your browser you need to run an HTTP server in the
root folder, for exemple using [`miniserve`]. You can then
browse the local web site at http://127.0.0.1:8080/index.html .

To add a new word in the dictionary, you must edit `dictionary/en.yaml` and
create a new entry for your word. You should set the `id` field to
`INSERT_WORD_ID`, and then run the command `npm run ids` in the `node` folder so
that `INSERT_WORD_ID` is automatically replaced with a random unique ID.

[`miniserve`]: https://lib.rs/crates/miniserve

## How to update a book

Books are made using [`mdbook`] and a few extensions which are written in [Rust].
First [install Rust] then run the following commands to install the required
binaries:

```
cargo install mdbook
cargo install mdbook-linkcheck
cargo install mdbook-regex-replacer
```

You can then open a terminal in the book folder (in which `book.toml` is
located) and run `mdbook serve`. This will run a web server that will reflect
changes that you make in the .md files.

[`mdbook`]: https://lib.rs/crates/mdbook
[install Rust]: https://www.rust-lang.org/tools/install