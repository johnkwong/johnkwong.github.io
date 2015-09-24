yout: post
title: MySQL - Connect to your database remotely
category: DevTools
tags: mysql
keywords: null
description: null
published: true
---

#### Step 1 Login to to remote MySQL database server.
You may login over ssh to remote database server as the root user.
`ssh root@mysqlserverip`

#### Step 2 Edit the my.cnf file
Edit /etc/mysql/my.cnf (Debian)
`vim /etc/mysql/my.cnf`
Make sure line skip-networking(Don’t listen for TCP/IP connections at all) is commented or remove line and add following line
`bind-address=YOUR-SERVER-IP`

#### Step 3 Restart MySql Server
`/etc/init.d/mysql restart`

#### Step 4 Creating a brand new user 
`mysql> GRANT ALL ON fooDatabase.* TO fooUser@'1.2.3.4' IDENTIFIED BY 'my_password';`

#### Step 4 Iptables allow MySql server incoming request on port 3306
`iptables -A INPUT -i eth0 -p tcp -m tcp --dport 3306 -j ACCEPT`

### Testing remotely
`# mysql -u fooUser -p -h 44.55.66.77`

