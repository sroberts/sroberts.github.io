# [sroberts.io](http://sroberts.io)

[![CircleCI](https://circleci.com/gh/sroberts/sroberts.github.io.svg?style=svg)](https://circleci.com/gh/sroberts/sroberts.github.io)

This is the source for my personal website, [sroberts.io](https://sroberts.io). It is built with Jekyll and hosted on GitHub Pages.

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