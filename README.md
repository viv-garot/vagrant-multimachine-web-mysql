# vagrant-multimachine-web

## Description
Create 2 vagrant boxes nginx webservers named web01 and web02 in a single VagrantFile with the VirtualBox provider

### Pre-requirements

* [Vagrant](https://www.vagrantup.com/downloads)
* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## How to use this repo

- Clone
- Boot the VMs
- Test

---

### Clone the repo

```
git clone https://github.com/viv-garot/vagrant-multimachine-web
```

### Change directory

```
cd vagrant-multimachine-web
```

### Start the boxes

```
vagrant up
```

### Sample output

```
vagrant up
Bringing machine 'web01' up with 'virtualbox' provider...
Bringing machine 'web02' up with 'virtualbox' provider...
==> web01: Importing base box 'vivien/nginx64'...
==> web01: Matching MAC address for NAT networking...
==> web01: Checking if box 'vivien/nginx64' version '21.07.07' is up to date...
==> web01: Setting the name of the VM: vagrant-multimachine-web_web01_1625736615755_33258
==> web01: Clearing any previously set forwarded ports...
==> web01: Clearing any previously set network interfaces...
==> web01: Preparing network interfaces based on configuration...
    web01: Adapter 1: nat
    web01: Adapter 2: hostonly
==> web01: Forwarding ports...
    web01: 80 (guest) => 8081 (host) (adapter 1)
    web01: 22 (guest) => 2222 (host) (adapter 1)
==> web01: Booting VM...
==> web01: Waiting for machine to boot. This may take a few minutes...

[...]

==> web02: Machine booted and ready!
==> web02: Checking for guest additions in VM...
==> web02: Setting hostname...
==> web02: Configuring and enabling network interfaces...
==> web02: Mounting shared folders...
    web02: /vagrant => /Users/viviengarot/Desktop/VisualCode/skillsmap/Vagrant/vagrant-multimachine-web
```

### Check the websites

- From the host CLI :

```
for f in 1 2 ; do echo "webserver web0$f" ;  curl localhost:808$f ; done
```

OR

```
for f in 1 2 ; do echo "webserver web0$f" ; curl 192.168.50.1$f ; done
```


- From the host web browser visit the following URLs :

  - [192.168.50.11](http://192.168.50.11)
  - [192.168.50.12](http://192.168.50.12)


![image](https://user-images.githubusercontent.com/85481359/124901469-58c76e80-dfe2-11eb-870d-67218bf66219.png)

