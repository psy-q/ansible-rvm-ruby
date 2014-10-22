# ansible-rvm-ruby

Allows installing RVM per user, along with any Ruby version you'd like that user to have.

It can also set a default Ruby version per user.

Stick this in your Ansible roles directory. I put it in `roles/ruby/rvm`.


## Adding to your own Ansible dir

If you stick reasonably closely to Ansible's recommended directory layout and if you keep your Ansible stuff in a git repo, you can add this role as a submodule:

    git submodule add https://github.com/psy-q/ansible-rvm-ruby.git roles/ruby/rvm_ruby
    git submodule init
    git submodule update

Of course you use a target path that's cooler than mine.
