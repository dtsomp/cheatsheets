# gpg cheatsheet

## Generation

Generate private key

    gpg --gen-key

## Public key administration

### My public keys

Export my public key

    gpg -a --export my@email.com > my@email.com.asc

### Other people's keys 

Import public gpg

    gpg --import <keyfile>

Get keys for a person

    gpg --list-keys <First name>

Find keys for a person

    gpg --keyserver <keyserver> --search-keys <user@email.com>

Get public key from keyserver

    gpg --keyserver <keyserver> --recv-keys <keyid>

Set trust level

    gpg --edit <firstname lastname>
    > trust
    > quit

## Secret keys administration

List secret keys

    gpg --list-secret-keys

Export secret key

    gpg --export-secret-key -a "User Name" > private.key


## Key servers

    hkp://pgp.mit.edu
    hkp://pool.sks-keyservers.net
