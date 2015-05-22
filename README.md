# DevStack with Swift Neutron &amp; LBaaS
Preconfigured DevStack (Snapshot from jenkins 21/05/2015) with Swift, Neutron &amp; LBaaSv2
##Intro
This repo was successfully tested on Ubuntu 14.04 (test date: 22/05/2015)

This repo was created for easy testing installation the latest version of DevStack (Juno) with Swift, Neutron &amp; LBaaSv2

##Pre-installation
Please check that you distro is updated
```sh
$ sudo apt-get update
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

This is your host ip: 10.0.2.15
Horizon is now available at http://10.0.2.15/
Keystone is serving at http://10.0.2.15:5000/
The default users are: admin and demo
The password: root

Go and check the installed DevStack

or 10.0.2.15 or localhost

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
####solution
```sh
$ ./clean.sh
```
and try again
```sh
$ ./stack.sh
