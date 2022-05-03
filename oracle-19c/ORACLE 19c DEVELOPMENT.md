# Development Setup

## Installation

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

### Destroy Oracle Database on VM

```shell
vagrant destroy
```

## Usage

### EM Browser Usage

```shell
https://localhost:5500/em/shell
```

### Command Line Usage

* [The installation RPM notes provide more details](https://docs.oracle.com/en/database/oracle/oracle-database/19/ladbi/running-rpm-packages-to-install-oracle-database.html#GUID-BB7C11E3-D385-4A2F-9EAF-75F4F0AACF02), this script creates a container database (ORCLCDB) with one pluggable database (ORCLPDB1) and configures the listener at the default port (1521).

* The default database connection parameters are:

```yml
    Hostname: localhost
    Port: 1521

    SID: ORCLCDB
    PDB: ORCLPDB1
    EM Express port: 5500
```

* Check the following message at the end of the installation.

```shell
ORACLE PASSWORD FOR SYS, SYSTEM AND PDBADMIN: MEiHD07VxX0=1
```

* Then test connection as DBA to default plugin database that has been created.

```shell
./bin/sql SYSTEM/MEiHD07VxX0=1@localhost/ORCLPDB1
```

* Test you can create a user.

```sql
CREATE USER john IDENTIFIED BY abcd1234;
```
