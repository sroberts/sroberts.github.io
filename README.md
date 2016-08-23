# sroberts.github.io

[![Circle CI](https://circleci.com/gh/sroberts/sroberts.github.io.svg?style=svg)](https://circleci.com/gh/sroberts/sroberts.github.io)

This is my attempt at a reasonable technical blog around security, programming, and any other things I decide counts.

## Author

**[Scott J Roberts](https://sroberts.github.io/about/)**

## Technology
* Blog Package: [Jekyll](http://jekyllrb.com)
* Blog Theme: [Lanyon](https://github.com/poole/lanyon) with my own [special modifications](http://i.imgur.com/qGh9V.jpg)
* Hosting: [GitHub Pages](http://pages.github.com)
* Todos: [GitHub Issues](https://github.com/sroberts/sroberts.github.io/issues)
* Testing: [HTMLProofer](https://github.com/gjtorikian/html-proofer) & [CircleCI](https://circleci.com/)

## Using Jekyll

* To get started run `bundle install` to get the necessary depenencies.
* Want to run it and see the blog locally? Just run `bundle exec jekyll serve`.
* Testing never hurts either, use `script/cibuild` to run tests locally.
* There are even fun utilities for creating posts thanks to [jekyll-compose](https://github.com/jekyll/jekyll-compose):
    * `jekyll draft`: Creates a new draft post with the given NAME
    * `jekyll post`: Creates a new post with the given NAME
    * `jekyll publish`: Moves a draft into the _posts directory and sets the date
    * `jekyll unpublish`: Moves a post back into the _drafts directory
    * `jekyll page`: Creates a new page with the given NAME

## License

Open sourced under the [MIT license](LICENSE.md).

<3
