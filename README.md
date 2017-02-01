# Dbljump API docs powered by Slate

Note that setup instructions are based on those in the [Slate readme at Github](https://github.com/lord/slate). Check there for the latest.

## Prerequisites

+ **Linux or OS X** — Windows may work, but is unsupported.
+ **Ruby, version 2.2.5 or newer**
+ **Bundler** — If Ruby is already installed, but the bundle command doesn't work, just run gem install bundler in a terminal.

## Installation

1. Clone this repository using the instructions on Bitbucket
2. Go to your clone's folder, e.g. `cd ~/slate`
3. Bundle and start the server

```
#either run this to run locally
bundle install
bundle exec middleman server

# OR run this to run with vagrant
vagrant up
```

## Usage

With the server running, you can now see the docs at http://localhost:4567.
