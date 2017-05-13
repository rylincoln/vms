## Vritual Machines

### Setup

* Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* Install [Vagrant](https://www.vagrantup.com/downloads.html)
* For Windows, install packer. `brew install packer`
* `vagrant box add ubuntu/trusty64`
* `vagrant box add ubuntu/xenial64`

```sh
git clone https://github.com/fulcrumapp/vms.git
cd vms
```

### Starting/Stopping/Destroying

To start up a machine, you run `vagrant up MACHINE`.

The basic commands are:

```
vagrant up MACHINE        # starts machine
vagrant halt MACHINE      # stops it, but doesn't destroy it
vagrant destroy MACHINE   # destroys the machine so you can easily start over with vagrant up MACHINE

vagrant ssh MACHINE       # SSH into the machine once it's booted
```

The machines defined in this repo are:

* `ubuntu14`
* `ubuntu16`
* `win10`

### Ubuntu 14.04 LTS 64bit

```
vagrant up ubuntu14
```

### Ubuntu 16.04 LTS 64bit

```
vagrant up ubuntu16
```

### Windows 10

First build the basebox:

```sh
git clone https://github.com/joefitzgerald/packer-windows.git
cd packer-windows
packer build windows_10.json
vagrant box add win10-x64 windows_10_virtualbox.box
```

Then from the `vms` directory:

```
vagrant up win10
```
