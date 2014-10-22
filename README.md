# ansible-rvm-ruby

Allows installing RVM per user, along with any Ruby version you'd like that user to have.

It can also set a default Ruby version per user.

Stick this in your Ansible roles directory. I put it in `roles/ruby/rvm`.

## Supported platforms

* Debian wheezy

It might work somewhere else, but I didn't check that. Canonical, they be mad.

## Example

This is how we can stick some Rubies on all our to-be-Rubified servers:

```
- hosts: rubified_servers
  roles:
    - { role: ruby/rvm_ruby, version: 2.1.1, user: rubyist }
    - { role: ruby/rvm_ruby, version: 2.1.3, user: rubyist }
    - { role: ruby/rvm_ruby, version: jruby-1.7.16, user: javahead }
```

The directory `ruby/rvm_ruby` in this case is just a subdirectory of roles where you cloned this role to, perhaps as a submodule.

Observe also that the `version` can be set to any version string that is valid for RVM, so you can install jRuby, Rubinius etc. with this role as well. If you choose to install jRuby, the OpenJDK 7 JRE will automatically be installed as well.

## Adding to your own Ansible dir

If you stick reasonably closely to Ansible's recommended directory layout and if you keep your Ansible stuff in a git repo, you can add this role as a submodule:

    git submodule add https://github.com/psy-q/ansible-rvm-ruby.git roles/ruby/rvm_ruby
    git submodule init
    git submodule update

Of course you use a target path that's cooler than mine.
