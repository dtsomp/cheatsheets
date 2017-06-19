# rspec-puppet

## About

Automated tests for your modules.

The instructions have been take mostly from the [official rspec-puppet tutorial](http://rspec-puppet.com/tutorial/)

## Installation

    sudo apt-get install ruby-rspec-puppet rake

Optionally, install puppet-lint
    
    sudo apt-get install puppet-lint


## Usage

### Initialization

You need to create the required file/dir structure.

    cd /path/to/mymodule
    rspec-puppet-init

### Run tests

    $ rake 
    /usr/bin/ruby2.3 /usr/bin/rspec --pattern spec/\*\*\{,/\*/\*\*\}/\*_spec.rb
    No examples found.


    Finished in 0.00029 seconds (files took 0.04553 seconds to load)
    0 examples, 0 failures

### Write tests

#### Basics

Test file naming:

    <thing-to-test>_spec.rb

Test file skeleton:

    require 'spec_helper'

    describe '<name of thing to test>' do
        # Insert test here
    end

