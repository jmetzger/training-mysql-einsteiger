# Server Vagrant - Testserver einrichten 

```
# Put this in a Vagrantfile 
# 1. mkdir project; cd project 
# 2. Put this in a Vagrantfile 
# 3. vagrant up 
# 4. vagrant ssh

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/focal64"
  config.vm.provision "shell", inline: <<-SHELL

    apt-get update 
    apt-get install -y mysql-server-8.0 wget 
    cd /usr/src 
    wget https://downloads.mysql.com/docs/sakila-db.tar.gz
    tar xzvf sakila-db.tar.gz 
    cd sakila-db
    mysql < sakila-schema.sql 
    mysql < sakila-data.sql

    echo "-- Setting up external user"
    echo "CREATE USER ext@'%' identified by 'student'" | mysql 
    echo "GRANT ALL PRIVILEGES ON *.* TO ext@'%'" | mysql 

    echo "-- Setting mysql up for external access" 
    echo "bind-address = 0.0.0.0" >> /etc/mysql/mysql.conf.d/mysqld.cnf
    systemctl restart mysql 

    echo "-- Setting up contributions database - big data" 
    cd /usr/src; 
    apt-get install -y git 
    git clone https://github.com/jmetzger/dedupe-examples.git;
    cd dedupe-examples; 
    cd mysql_example; 
    echo "set global local_infile = 1" | mysql
    echo "# Eventually you need to enter (in mysql_example/mysql.cnf)"  
    echo '# Only necessary if you cannot connect to db by entering "mysql"' 
    echo '# password=<your_root_pw>' 
    ./setup.sh 
    date 
    echo "-- Done -  Setting up contributions database - big data" 
  SHELL
end
```
