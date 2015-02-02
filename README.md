# doomkin/oracle-xe Dockerfile

Oracle Database Express Edition 11g Release 2 with SSH key access on Ubuntu 14.04.1 LTS Dockerfile for trusted automated Docker builds.

This **Dockerfile** is a [trusted build](https://registry.hub.docker.com/u/doomkin/oracle-xe/) of [Docker Registry](https://registry.hub.docker.com/).

### Installation
```
sudo docker pull doomkin/oracle-xe
```

### Run
```
sudo docker run --name oracle-xe -d -P doomkin/oracle-xe
```

### Connect database
```
hostname: localhost
port: `sudo docker port oracle-xe 1521 | cut -d":" -f2`
sid: xe
username: system
password: oracle
```

Password for SYS & SYSTEM
```
oracle
```

### Apex control
```
http://localhost:`sudo docker port oracle-xe 8080 | cut -d":" -f2`
```

### Login by SSH
```
ssh-agent -s
ssh-add ssh/id_rsa
ssh root@localhost -p `sudo docker port oracle-xe 22 | cut -d":" -f2`
```
