#   Heroku Buildpack Guide For Rails

1.  Use Multiple Buildpacks

        $ heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git

    create `.buildpacks` file, and add a uri into file.

        $ cat .buildpacks
        https://github.com/heroku/heroku-buildpack-ruby.git

2.  Upgrade OpenSSL

        $ cat .buildpacks
        https://github.com/heroku/heroku-buildpack-ruby.git
        https://github.com/gtank/ossl-buildpack.git

3.  Speed Up Assets Precompilation

        $ cat .buildpacks
        https://github.com/enricheers/heroku-buildpack-ruby.git
        https://github.com/gtank/ossl-buildpack.git

    add these line into `Gemfile`.

        group :assets do
          ...
          gem 'turbo-sprockets-rails3'
        end
