# rbenv

- [rbenv](https://github.com/rbenv/rbenv)
- [rbenv-installer](https://github.com/rbenv/rbenv-installer)
- [rbenv on ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-18-04)

## Installation (Ubuntu 18.04)

### Update package manager

```sh
sudo apt update
```

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

### Use rbenv to install different versions of Ruby

List the available versions of Ruby

```sh
rbenv install -l
```

Install a Ruby version

```sh
rbenv install 2.7.1
```