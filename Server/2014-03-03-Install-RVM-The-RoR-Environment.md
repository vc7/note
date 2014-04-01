Install RVM - The RoR Environment
======

RVM - [Ruby Version Manager](http://rvm.io/)

Installing
------

```
curl -L get.rvm.io | bash -s stable
```

This will install the `RVM` for us, and adding additional settings in files `.bashrc` and `.bash_profile`.

#### `soutce` the rvm

```
source ~/.rvm/scripts/rvm
```

#### Checkout requirements for Ruby before installing

```
rvm requirements
```

Installing Ruby
------

```
rvm install 2.1.0
```

Set the **default** using version with `--default` flag

```
rvm --default use 2.1.0
```

Installing Rails
------

```
gem install rails -v 4.0.2
```

References
------

[The Life of a Radar - Ubuntu, Ruby, RVM, Rails, and You](http://ryanbigg.com/2010/12/ubuntu-ruby-rvm-rails-and-you/)
