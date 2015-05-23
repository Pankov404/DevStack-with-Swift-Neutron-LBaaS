# DevStack with Swift, Neutron &amp; LBaaS
Preconfigured DevStack with Swift, Neutron &amp; LBaaSv2

##Intro
This repo was successfully tested on Ubuntu 14.04 with VirtualBox 4.3.28 (test date: 23/05/2015) 

This repo was created for easy testing installation the latest version of DevStack with Swift, Neutron &amp; LBaaSv2

It also automatically enables IPv4 by default and disables IPv6 

##Pre-installation
Please check that you distro is updated
```sh
$ sudo apt-get update
$ sudo apt-get install git
$ sudo apt-get -y upgrade 
$ sudo apt-get -y dist-upgrade 
$ sudo apt-get update
```

##Getting DevStack
```sh
$ git clone https://github.com/Pankov404/DevStack-with-Swift-Neutron-LBaaS
```
##Installation & Running 
```sh
$ sudo chmod 755 -R DevStack-with-Swift-Neutron-LBaaS
$ cd DevStack-with-Swift-Neutron-LBaaS
$ ./stack.sh
```
It takes some time, so be patient

##Finish

```sh
This is your host ip: 10.0.2.15
Horizon is now available at http://10.0.2.15/
Keystone is serving at http://10.0.2.15:5000/
The default users are: admin and demo
The password: root
```
Go and check the installed DevStack on 10.0.2.15 or localhost

##Troubleshooting
###507 ERROR
2015-05-22 14:55:14.951 | [ERROR] /home/stack/DevStack-with-Swift-Neutron-LBaaS/functions-common:507 git call failed: [git clone git://git.openstack.org/openstack/requirements.git /opt/stack/requirements]
2015-05-22 14:55:15.959 | Error on exit
####solution
```sh
$ git config --global url.https://github.com/.insteadOf git://git.openstack.org/
```
and try again
```sh
$ ./stack.sh
```
###Any others problems during installation
####general solution
try to clean and unstack
```sh
$ ./clean.sh
$ ./unstack.sh
```
and try re-stack again
```sh
$ ./stack.sh
```
if it still doesn't work try to reboot OS and start again.

Good Luck! :)
