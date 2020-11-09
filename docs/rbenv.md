# rbenv

- [rbenv](https://github.com/rbenv/rbenv)
- [rbenv-installer](https://github.com/rbenv/rbenv-installer)
- [rbenv on ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-18-04)

## Installation (Ubuntu 18.04)

### Update package manager

```sh
sudo apt update
```

### Install dependencies required for Ruby

```sh
sudo apt install autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm5 libgdbm-dev
```
See [ruby-build wiki](https://github.com/rbenv/ruby-build/wiki#suggested-build-environment) for other versions of Ubuntu

### Use rbenv installer to install rbenv

```sh
wget -q https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-installer -O- | bash
```

Add rbenv to PATH

```sh
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
```

Set up rbenv

```sh
~/.rbenv/bin/rbenv init
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
source ~/.bashrc
```

Veryify that rbenv is properly installed using rbenv-installer doctor script

``` sh
wget -q https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor -O- | bash
```

The output should look something like this:

```sh
Checking for `rbenv' in PATH: /usr/local/bin/rbenv
Checking for rbenv shims in PATH: OK
Checking `rbenv install' support: /usr/local/bin/rbenv-install (ruby-build 20170523)
Counting installed Ruby versions: none
    There aren't any Ruby versions installed under `~/.rbenv/versions'.
    You can install Ruby versions like so: rbenv install 2.2.4
Checking RubyGems settings: OK
Auditing installed plugins: OK
```

NOTE: using rbenv-installer automatically installs [ruby-build](https://github.com/rbenv/ruby-build) which provides the `rbenv install` command

## Usage 

### Use rbenv to install different versions of Ruby

List the available versions of Ruby

```sh
rbenv install -l
```

Install a Ruby version

```sh
rbenv install 2.7.1
```

Check which versions of Ruby are installed (version with * next to it is currently active)

```sh
rbenv versions
```

Set the default (global) version of Ruby to use.  If this isnt set it will try to use `system` which looks for the sytem installed Ruby (detected by searching your `$PATH`)

```sh
rbenv global 2.7.1
```

`rbenv global` will report the currently configured global version

Set a local version

```sh
rbenv local 2.6.6
```

This sets a local application specific version by writing the version name to a `.ruby-version` file in the current directory.
