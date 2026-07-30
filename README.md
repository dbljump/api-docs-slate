# Dbljump API docs powered by Slate

This repository uses the legacy [Slate](https://github.com/slatedocs/slate)
documentation toolchain.

## Prerequisites

+ **Linux or macOS**
+ **Ruby 2.6.7** — selected automatically by `.ruby-version` when using rbenv
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
bundle exec middleman build --clean
```

## Publishing to GitHub Pages

Commit changes to master branch, then run the deploy script:

```sh
./deploy.sh
```

The deploy script builds the site and pushes the generated output to the
`gh-pages` branch.
