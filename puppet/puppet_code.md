Generate a random number on node. It's always the same, given that the node and the text are the same.

    $random_number = fqdn_rand(24, 'mystring')
    notice("This is my random ${random_number}")

    $ puppet apply /vagrant/test.pp
    Notice: Scope(Class[main]): This is my random 7

