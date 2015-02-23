#IGOS Nusantara Vagrant Box

* Install GCC & kernel devel
```
# yum install gcc kernel-devel
```

* install Virtualbox Guest
* create vagrant user
```
# useradd -m -d /home/vagrant vagrant
# echo "vagrant" | passwd "vagrant" --stdin
```

* add authorized_keys to /vagrant/.ssh
```
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEA6NF8iallvQVp22WDkTkyrtvp9eWW6A8YVr+kz4TjGYe7gHzIw+niNltGEFHzD8+v1I2YJ6oXevct1YeS0o9HZyN1Q9qgCgzUFtdOKLv6IedplqoPkcmF0aYet2PkEDo3MlTBckFXPITAMzF8dJSIFo9D8HfdOV0IAdx4O7PtixWKn5y2hMNG0zQPyUecp4pzC6kivAIhyfHilFR61RGL+GPXQ2MWZWFYbAGjyiYJnAmCP3NOTd0jMZEnDkbUvxhMmBYSdETk1rRgm+R4LOzFUGaHqHDLKLX+FIPKcF96hrucXzcWyLbIbEgE98OHlnVYCzRdK8jlqm8tehUc9c9WhQ== vagrant insecure public key
```

* edit /etc/sudoers
```
vagrant ALL=(ALL) NOPASSWD: ALL
#Defaults    requiretty
```

* Creating a base box
```
vagrant package --base vagrantboxbase --output ign-2.0-server.box
```

* Testing the box
```
$ vagrant box add my-box /path/to/the/ign-2.0-server.box
$ vagrant init my-box
$ vagrant up
```
