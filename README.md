Heroku buildpack: ZX Spectrum
=============================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpack) for ZX Spectrum roms. It uses [jsspeccy](http://matt.west.co.tt/spectrum/jsspeccy/) to run 48k ZX Spectrum roms that are pushed to a heroku application.

This buildpack is closely based on the [NES buildpack](https://github.com/hone/heroku-buildpack-jsnes) by [Terence Lee](https://twitter.com/hone02).

Usage
-----

### ZX Spectrum

Example Usage:

    $ ls
    game.sna

    $ heroku create --stack cedar --buildpack http://github.com/metadaddy-sfdc/heroku-buildpack-jsspeccy.git

    $ git push heroku master
    ...
    -----> Heroku receiving push
    -----> Fetching custom buildpack
    -----> ZX Spectrum game detected
    -----> Installing dependencies using Bundler version 1.1.rc
           Running: bundle install --without development:test --path vendor/bundle --deployment
           Fetching gem metadata from http://rubygems.org/..
           Installing rack (1.3.5)
           Using bundler (1.1.rc)
           Your bundle is complete! It was installed into ./vendor/bundle
           Cleaning up the bundler cache.
    -----> Discovering process types
           Procfile declares types -> (none)

The buildpack will detect your app as ZX Spectrum if it has a `*.sna` file in the root directory. 

