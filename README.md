# Red Hat Community website

To get started, you need to have Ruby and Ruby Gems installed, as well
as "bundler".


## Initial setup

```
sudo yum install -y ruby-devel rubygems gcc-c++ curl-devel rubygem-bundler
git clone --recursive git@gitlab.osas.lab.eng.rdu2.redhat.com:garrett/community-middleman.git
cd community-middleman
bundle install
```

If you don't clone the repo with `--recursive`, make sure to run
`git submodule init && git submodule update`


## Running

As we're using gems locally with bundler, you need to run via `bundle exec`:

```
bundle exec middleman server
```

('server' is optional, but it helps if you're going through
command-history in bash or zsh with control-r, versus other middleman
commands like `console`, `build`, or `deploy`)


## Updating

When there are new gems in `Gemfile`, just run `bundle` again.


## Customizing your site

The site can be easily customized by editing `data/site.yml`.


## Deploying

### Setting up deployment

FIXME: Right now, please reference data/site.yml

### Actual deployment

You'll need to be added to the `osasteam` group on OpenShift and have
your public key added to your profile.

Afterward, deployment is a simple single command:

```
bundle exec middleman deploy
```
