# Vagrant

## Getting started

The four basic commands:

    vagrant init hashicorp/precise64        # Init the current dir with a Ubuntu 14.04 box.
                                            # Only need to run this once for the current dir.
                                            # Creates Vagrantfile.

    vagrant up                              # Start the VM.
    vagrant ssh                             # Connect to the started VM.
    vagrant destroy                         # Kill VM and all data with it.

## Useful commands

    vagrant status                          # Check status of VM (duh)
    vagrant destroy -f                      # Destroy without asking
    vagrant halt                            # Stop the VM but KEEP CHANGES/DATA (aka don't destroy)

    vagrant box add my-box /path/to/new.box   # Add new.box as "my-box" in my local list of available boxes
    vagrant box init my-box                   # Now initialize the current dir with it


## Configuration

All configuration takes place in the local Vagrantfile.
You can copy paste the following into a Vagrantfile and adjust accordingly.

    Vagrant.configure(2) do |config|

    # BOX

    # Use this box (if not locally added, will try to grab it from https://atlas.hashicorp.com/search)
    config.vm.box = "hashicorp/precise64"

    # SYNCED FOLDERS

    # By default, the current folder is by default synced as /vagrant on the VM.
    # I also want my Puppet modules dir synced to /opt/puppet-modules on the VM.
    config.vm.synced_folder "/home/dtsomp/WORKSPACE/git/puppet/puppet-modules", "/opt/puppet-modules"

    # PORT FORWARDING

    #  Examples of port forwarding. Add as many of these lines as needed.
    #  config.vm.network "forwarded_port", guest: 80, host: 80   

    # VIRTUAL HARDWARE

    config.vm.provider "virtualbox" do |vb|
     vb.memory = "2048"
     vb.cpus = "2"
    end

    # PROVISIONING

    # Uncomment to run bootstrap.sh when the VM is up.
    # (you'll of course need a bootstrap.sh in the same path as this Vagrantfile)
    # config.vm.provision :shell, path: "bootstrap.sh"


## Box creation

Steps to create a box from scratch. I usually use Virtualbox for this.

1. Start up Virtualbox and create a VM.
  - Allow for large disk size, but make sure it's dynamically resized.
  - Disable USB, Audio, floppy and anything not needed.
  - Network adapter 1 needs to use NAT.
2. Install OS.
  - hostname: vagrant
  - user/pass: vagrant
3. Software
  - Make sure openssh-server is installed.
  - Install the rest of your software (beware of future box size).
4. Configuration
  - visudo
    - Add this **after** the #includedir line: `vagrant ALL=(ALL) NOPASSWD: ALL`
  - sshd
    - Add `Use DNS no` at the end of sshd_config to disable DNS lookups. Faster SSH while not connected to the Internet.
  - Vagrant ssh key
    - `mkdir ~/.ssh`
    - `wget -O ~/.ssh/authorized_keys https://raw.githubusercontent.com/mitchellh/vagrant/master/keys/vagrant.pub`
    - `chmod 0700 ~/.ssh`
    - `chmod 0600 ~/.ssh/authorized_keys`
5. Virtualbox additions
  - `sudo apt-get install linux-headers-$(uname -r) build-essential dkms`
  - From the Virtualbox menu, Insert the Guest Additions CD Image.
  - `sudo mount /dev/cdrom /media/cdrom`
  - `sudo sh /media/cdrom/VBoxLinuxAdditions.run`
6. Clean up to reduce box size
  - `sudo apt-get clean`
  - Zero-out the rest of the disk
    - `sudo dd if=/dev/zero of=/EMPTY bs=1M`
    - `sudo rm -f /EMPTY`
  - Clear history and exit
    `cat /dev/null > ~/.bash_history && history -c && exit`
7. Shutdown the VM.
8. Package and rename.
  - `vagrant package --base name-of-my-virtual-machine`
  - `mv package.box my-box.box`


You can now add it and test it out:

    vagrant box add my-box /path/to/my-box.box
    vagrant init my-box
    vagrant up && vagrant ssh
