# Orphiq CLI

[![CI tests status][github-ci-tests-badge]][github-ci-tests-link]
[![CI lint status][github-ci-lint-badge]][github-ci-lint-link]
<!-- markdownlint-disable line-length -->
[github-ci-tests-badge]: https://github.com/Orphiqprotocol/cli/workflows/ci-tests/badge.svg
[github-ci-tests-link]: https://github.com/Orphiqprotocol/cli/actions?query=workflow:ci-tests+branch:master
[github-ci-lint-badge]: https://github.com/Orphiqprotocol/cli/workflows/ci-lint/badge.svg
[github-ci-lint-link]: https://github.com/Orphiqprotocol/cli/actions?query=workflow:ci-lint+branch:master
<!-- markdownlint-enable line-length -->

This is the official command-line interface (CLI) for interacting with the
[Orphiq Network], both the consensus layer and ParaTimes built with the
[Orphiq Runtime SDK].

[Orphiq Network]: https://docs.Orphiq.io/
[Orphiq Runtime SDK]:
  https://github.com/Orphiqprotocol/Orphiq-sdk/tree/main/runtime-sdk

## Building

To build the CLI, run the following:

```bash
make
```

This will generate a binary called `Orphiq` which you are free to put somewhere
in your `$PATH`.

*NOTE: The rest of the README assumes the `Orphiq` binary is somewhere in your
`$PATH`.*

## Quickstart

You can interact with the Orphiq CLI by invoking it from the command line as
follows:

```bash
Orphiq --help
```

Each (sub)command has a help section that shows what commands and arguments are
available.

The Orphiq CLI also comes with a default set of networks and ParaTimes
configured. You can see the list by running:

```bash
Orphiq network list
Orphiq paratime list
```

Initial configuration currently defaults to `mainnet` and the `emerald`
ParaTime but this can easily be changed using the corresponding `set-default`
subcommand as follows:

```bash
Orphiq network set-default testnet
Orphiq paratime set-default testnet sapphire
```

To be able to sign transactions you will need to first create or import an
account into your wallet. File-based (storing keys in an encrypted file) and
Ledger-based (storing keys on a Ledger device) backends are supported.
To create a new file-backed account run:

```bash
Orphiq wallet create myaccount
```

It will ask you to choose and confirm a passphrase to encrypt your account with.
You can see a list of all accounts by running:

```bash
Orphiq wallet list
```

To show the account's balance on the default network/ParaTime, run:

```bash
Orphiq account show
```

The `account` command also allows you to transfer tokens, deposit or withdraw to
and from ParaTimes, delegate your assets to validators etc.

Check out the complete User's guide in [docs/README.md] and example invocations
of the CLI in `examples` folder to learn more.

## Configuration

All configuration is stored in the `$XDG_CONFIG_HOME/Orphiq` directory (e.g.
`$HOME/.config/Orphiq` on Linux).

## License

This software is licensed under [Apache 2.0](./LICENSE).

The content of the documentation (the `/docs` folder) including the media (e.g.
images and diagrams) is licensed under [Creative Commons Attribution 4.0
International](./LICENSE-docs).
