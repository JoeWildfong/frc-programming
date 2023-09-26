FRC Programming
===============

This is the source code for the FRC Programming guide available to read [here].

[here]: https://joewildfong.github.io/frc-programming

Development
-----------

The guide is developed with [mdBook] and the [mdbook-mermaid] plugin.
If you have a Rust toolchain installed, you can install both with

```sh
cargo install mdbook
cargo install mdbook-mermaid
```

Alternatively, static binaries are available on GitHub at the above links.

[markdownlint] (available as an extension for [VSCode] / [Sublime Text] / [(Neo)vim]) is recommended for development,
as it's run in CI and will block merges.

[mdBook]: https://github.com/rust-lang/mdBook
[mdbook-mermaid]: https://github.com/badboy/mdbook-mermaid
[markdownlint]: https://github.com/DavidAnson/markdownlint
[VSCode]: https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint
[Sublime Text]: https://packagecontrol.io/packages/SublimeLinter-contrib-markdownlint
[(Neo)vim]: https://github.com/fannheyward/coc-markdownlint
