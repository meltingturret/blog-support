# dev-env-for-oracle-19c

## Install

### Vagrant
```shell
cd workspace/oracle
curl -O https://releases.hashicorp.com/vagrant/2.2.9/vagrant_2.2.9_x86_64.deb
sudo apt install ./vagrant_2.2.9_x86_64.deb
```

### Virtualbox
```shell
sudo apt install virtualbox
sudo apt install virtualbox-ext-pack -y
```

### Oracle Vagrant Projects
```shell
git clone https://github.com/oracle/vagrant-projects
cd vagrant-projects/OracleDatabase/19.3.0
```

### Running Oracle Database on VM

[Download the installation linux zip file into the 19.3.0 directory before running the vagrant command, do not unzip the zip file.](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index.html)

```shell
vagrant up
```

### Halting Oracle Database on VM

```shell
vagrant halt
```

## Example Usage

* [The installation RPM notes provide more details](https://docs.oracle.com/en/database/oracle/oracle-database/19/ladbi/running-rpm-packages-to-install-oracle-database.html#GUID-BB7C11E3-D385-4A2F-9EAF-75F4F0AACF02)

* The default database connection parameters are:

```yml
    Hostname: localhost
    Port: 1521
    SID: ORCLCDB
    PDB: ORCLPDB1
    EM Express port: 5500
```

* Database passwords are auto-generated and printed on install

* Connection test to the container database

```shell
./bin/sql system/Vi7PdjdVhXg=1@localhost/ORCLCDB
```

* This script creates a container database (ORCLCDB) with one pluggable database (ORCLPDB1) and configures the listener at the default port (1521). 

