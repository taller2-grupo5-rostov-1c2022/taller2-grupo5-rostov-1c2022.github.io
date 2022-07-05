[![pages-build-deployment](https://github.com/taller2-grupo5-rostov-1c2022/taller2-grupo5-rostov-1c2022.github.io/actions/workflows/pages/pages-build-deployment/badge.svg?branch=master)](https://github.com/taller2-grupo5-rostov-1c2022/taller2-grupo5-rostov-1c2022.github.io/actions/workflows/pages/pages-build-deployment)

# Taller 2 - Grupo 5 - Rostov 1C2022

This documentation is based on [Jekyll](https://jekyllrb.com/) with [just-the-docs](https://just-the-docs.github.io/just-the-docs/) theme.

## Dependencies

This project needs the following dependencies in the following order:

[Ruby](https://www.ruby-lang.org/en/documentation/installation/)

```bash
sudo apt-get install ruby-full
```
[Bundler](https://bundler.io/) and [Jekyll](https://jekyllrb.com/)

```bash
gem install jekyll bundler
```

Once you have them installed and this repo is cloned, you can run the following command to install the local dependencies from `Gemfile`:

```bash
bundle config set --local path 'vendor/bundle'
bundle install
```

## Docker

Run the following command in the project root to build the docker image:

```bash
$ docker-compose up --build
```


## Local Development

Just run:

```bash
bundle exec jekyll serve --incremental
```






