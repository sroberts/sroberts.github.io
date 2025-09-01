# [sroberts.io](http://sroberts.io)

[![CircleCI](https://circleci.com/gh/sroberts/sroberts.github.io.svg?style=svg)](https://circleci.com/gh/sroberts/sroberts.github.io)

This is the source for my personal website, [sroberts.io](https://sroberts.io). It is built with Jekyll and hosted on GitHub Pages.

## System Setup

This project uses [mise](https://mise.jdx.dev/) to manage the Ruby version. If you have `mise` installed, you can just run `mise install` in the root of the project to install the correct Ruby version.

Alternatively, you can use `rbenv` to manage your Ruby version.

### macOS

Using [Homebrew](https://brew.sh/), install `rbenv`:

```bash
brew install rbenv
```

Then, follow the instructions to initialize `rbenv` in your shell. Once that is complete, install Ruby:

```bash
rbenv install
```

### Linux

#### Debian/Ubuntu-based

```bash
sudo apt-get update
sudo apt-get install -y rbenv
```

Then, follow the instructions to initialize `rbenv` in your shell. Once that is complete, install Ruby:

```bash
rbenv install
```

#### Arch-based

```bash
pacman -S rbenv
```

Then, follow the instructions to initialize `rbenv` in your shell. Once that is complete, install Ruby:

```bash
rbenv install
```

### Installing Bundler

Once Ruby is installed, you can install Bundler:

```bash
gem install bundler
```

## Local Development

To get started, you will need to have Ruby and Bundler installed. Then, you can clone the repository and install the dependencies:

```bash
git clone https://github.com/sroberts/sroberts.github.io.git
cd sroberts.github.io
bundle install
```

Once the dependencies are installed, you can start the Jekyll server:

```bash
bundle exec jekyll serve
```

This will start a local web server at `http://localhost:4000`.

## Deployment

This site is automatically deployed using GitHub Pages. Any changes pushed to the `master` branch will be automatically built and deployed.

## Content Management

The content for the site is located in the root directory in Markdown files. To add a new page, you can create a new Markdown file in the root directory. The navigation is managed in `_config.yml`.

## Technical

- Jekyll
- Template: [Solo](http://chibicode.github.io/solo)

## Legal

This is my personal web site. The opinions expressed herein represent my own, and not those of any employer, group, or organization.

© 2017. All rights reserved.