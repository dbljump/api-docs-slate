# Dbljump API docs powered by Slate

This repository uses the legacy [Slate](https://github.com/slatedocs/slate)
documentation toolchain.

## Prerequisites

+ **Linux or macOS**
+ **Ruby 2.6.x** — `.ruby-version` selects 2.6.7 when using rbenv;
  macOS system Ruby 2.6.10 also works.
+ **Bundler 1.17.2**

## Installation

Clone the repository, install its locked dependencies, and start the local
preview server:

```sh
git clone https://github.com/dbljump/api-docs-slate.git
cd api-docs-slate
bundle install
bundle exec middleman server
```

## Local

With the server running, view the docs at <http://localhost:4567>.

To verify a production build:

```sh
./deploy.sh --build-only
```

The script uses the active Ruby when it is 2.6.x. On macOS it falls back to
`/usr/bin/ruby` if that is a compatible 2.6.x runtime. This lets deployment
work when mise selects a newer Ruby for other projects. To select an explicit
Ruby executable, set `SLATE_RUBY=/path/to/ruby`.

It runs Bundler 1.17.2 with the selected Ruby and installs missing locked gems
into the ignored `vendor/bundle` directory. An explicit `BUNDLE_PATH` is also
supported. No administrator privileges are needed for these project gems.

If you see `undefined method 'untaint'`, Bundler 1.17.2 is running with an
incompatible modern Ruby. Installing that Bundler under Ruby 3 does not fix
the mismatch; use the compatible Ruby runtime instead. `bundler: command not
found: middleman` means the project's bundled gems have not been installed
for the selected runtime and bundle path.

## Publishing to GitHub Pages

Commit changes to master branch, then run the deploy script:

```sh
./deploy.sh
```

The deploy script builds the site and pushes the generated output to the
`gh-pages` branch. `--build-only` never commits or pushes; `--help` displays
the available options without building.
