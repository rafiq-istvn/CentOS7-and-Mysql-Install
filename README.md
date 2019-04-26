# CentOS7-and-Mysql-Install
centos7, MySQL, Virtual Box, Vagrant, MysqlWorkbench, Apache server Install and run.

1.Insatlling centos7 and vagrant with oracle virtual box:
--------------------------------------------------------------

1. Download and install Oracle Virtual box
2. Download and inastall Vagrant
3. create Folder: vagrant/centos7/
4. Open gitbash in that folder
```
$ vagrant init
```
6. Open VagrantFile and edit config.vm.box = "centos/7" this.
```
$ vagrant up
$ vagrant ssh
```
Done !

</br> </br>
<a href="https://imgur.com/MSlCAOm"><img src="https://i.imgur.com/MSlCAOm.png" title="source: imgur.com" /></a>

2.Installing Mysql:
---------------------
Go to "/vagrant/centos7/" folder and open git bush.

First Install this after install of CentOS:
---------------------------------------------
```
$ vagrant plugin install vagrant-vbguest
$ vagrant destroy && vagrant up
```
Before install MySQL:
------------------------
```
$ vagrant ssh
$ hostname
$ hostname -f
$ sudo yum update
$ sudo yum install wget
```
MySql Instalation in CentOS:
-----------------------------
```
$ wget https://dev.mysql.com/get/mysql80-community-release-el7-2.noarch.rpm
$ md5sum mysql80-community-release-el7-2.noarch.rpm
$ sudo rpm -ivh mysql80-community-release-el7-2.noarch.rpm
$ sudo yum install mysql-server
$ sudo systemctl start mysqld
$ sudo systemctl status mysqld
$ sudo grep 'temporary password' /var/log/mysqld.log
[Remember This Password]
$ sudo mysql_secure_installation
$ mysqladmin -u root -p version
```
3.Connect Mysql Workbench with vagrant centos7
-----------------------------------------------
1. Got the centos7 and open CLI:

    $ vagrant ssh-config

2. Then Open MySQL Workbench
3. Open New Connection
```
Connection Name: vagrant mysql
ConnectionType: Standard TCP/IP over SSH
SSh Hostname: 127.0.0.1:2222
SSh Username: vagrant
SSH Key File: F:/Vagrant/CentOS/.vagrant/machines/default/virtualbox/private_key
MySQL Hostname: 127.0.0.1
MySQL Server Port: 3306
Username: root
```
4. Press: Test Connection.
5. press ok.

4.Installing Apache in centos7:
----------------------------------
Do--> apache install centos7.txt
