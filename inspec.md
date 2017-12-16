# InSpec

## Installation

[Download package](https://downloads.chef.io/inspec)

## Usage

Create profile named 'foobar':

    inspec init profile foobar

Run against remote server:

    inspec exec foobar -t ssh://user@remoteserver [ -t sshkey.rsa ]
