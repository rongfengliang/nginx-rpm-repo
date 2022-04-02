# nginx for rpm repo


## how to do 

* running centos 

```code
docker run -it -v $PWD/packages:/opt/packages rpmbuild/centos7 sh
sudo -i
yum install -y createrepo 
cd /opt/packages
createrepo .
```

## startning nginx webserver

```code
docker-compose up -d
```

## usage yum repo

* conf repo

```code
docker run -it  centos:centos7 sh

touch  /etc/yum.repos.d/kp.repo

[kp-repo]
name=mydemo
baseurl=http://<nginxserviceip or externel service ip>
enabled=1
gpgcheck=0

yum install  keepalived
```

## result

```code
Dependencies Resolved

===========================================================================================================================================
 Package                               Arch                  Version                                          Repository              Size
===========================================================================================================================================
Installing:
 keepalived                            x86_64                2.2.7-1.el7                                      kp-repo                537 k
Installing for dependencies:
 ipset-libs                            x86_64                7.1-1.el7                                        base                    64 k
 iptables                              x86_64                1.4.21-35.el7                                    base                   432 k
 libmnl                                x86_64                1.0.3-7.el7                                      base                    23 k
 libnetfilter_conntrack                x86_64                1.0.6-1.el7_3                                    base                    55 k
 libnfnetlink                          x86_64                1.0.1-4.el7                                      base                    26 k
 libnl3                                x86_64                3.2.28-4.el7                                     base                   278 k
 lm_sensors-libs                       x86_64                3.4.0-8.20160601gitf9185e5.el7                   base                    42 k
 mariadb-libs                          x86_64                1:5.5.68-1.el7                                   base                   760 k
 net-snmp-agent-libs                   x86_64                1:5.7.2-49.el7_9.1                               updates                707 k
 net-snmp-libs                         x86_64                1:5.7.2-49.el7_9.1                               updates                751 k
 tcp_wrappers-libs                     x86_64                7.6-77.el7                                       base                    66 k
```
