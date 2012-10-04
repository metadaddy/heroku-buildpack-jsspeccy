Heroku buildpack: ZX Spectrum
=============================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpack) for ZX Spectrum roms. It uses [jsspeccy](http://matt.west.co.tt/spectrum/jsspeccy/) to run 48k ZX Spectrum roms that are pushed to a heroku application. For example, here's [Manic Miner](http://blooming-fire-1627.herokuapp.com/).

This buildpack is closely based on the [NES buildpack](https://github.com/hone/heroku-buildpack-jsnes) by [Terence Lee](https://twitter.com/hone02).

Usage
-----

### ZX Spectrum

Example Usage:

    $ ls
    game.sna

    $ heroku create --stack cedar --buildpack http://github.com/metadaddy-sfdc/heroku-buildpack-jsspeccy.git

    $ git push heroku master
    Counting objects: 3, done.
    Delta compression using up to 4 threads.
    Compressing objects: 100% (2/2), done.
    Writing objects: 100% (3/3), 14.22 KiB, done.
    Total 3 (delta 0), reused 0 (delta 0)

    -----> Heroku receiving push
    -----> Fetching custom buildpack... done
    -----> JSSPECCY app detected
    -----> Installing dependencies using Bundler version 1.1.rc
           Running: bundle install --deployment
           Fetching gem metadata from http://rubygems.org/..
           Installing rack (1.4.1)
           Using bundler (1.1.rc)
           Your bundle is complete! It was installed into ./vendor/bundle
    -----> Discovering process types
           Procfile declares types    -> (none)
           Default types for JSSPECCY -> web
    -----> Compiled slug size is 932K
    -----> Launching... done, v5
           http://manic-miner-6031769.herokuapp.com deployed to Heroku

    To git@heroku.com:manic-miner-6031769.git
     * [new branch]      master -> master
    
The buildpack will detect your app as ZX Spectrum if it has a `*.sna` file in the root directory. 

