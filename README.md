# Taller 2 - Grupo 5 - Rostov 1C2022

This documentation is based on [Jekyll](https://jekyllrb.com/) with [just-the-docs](https://just-the-docs.github.io/just-the-docs/) theme.

## Dependencies

This project needs the following dependencies in the following order:

[Ruby](https://jekyllrb.com/)

```bash
sudo apt-get install ruby-full
```
[Bundler](https://bundler.io/) and [Jekyll](https://bundler.io/)

```bash
gem install jekyll bundler
```

Once you have them installed and this repo is cloned, you can run the following command to install the local dependencies from Gemfile:

```bash
bundle config set --local path 'vendor/bundle'
bundle install
```

## Local Development

Just run:

```bash
bundle exec jekyll serve --incremental
```






