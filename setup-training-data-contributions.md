# Setup training data contributions 

## Walkthrough (Debian/Ubuntu 18.04. with mysql 5.7.)

  * Complete process takes about 10 minutes 

```bash 
cd /usr/src; 
apt update; apt install git; 
git clone https://github.com/jmetzger/dedupe-examples.git;
cd dedupe-examples; 
cd mysql_example; 
# Eventually you need to enter (in mysql_example/mysql.cnf)  
# Only necessary if you cannot connect to db by entering "mysql" 
# password=<your_root_pw> 
./setup.sh 
```

## Walkthrough (Debian/Ubuntu 20.04. with mysql 8)

  * Complete process takes about 10 minutes 

```bash 
cd /usr/src; 
apt update; apt install git; 
git clone https://github.com/jmetzger/dedupe-examples.git;
cd dedupe-examples; 
cd mysql_example; 
# otherwice script does not work 
echo "set local_infile=1" | mysql
# Eventually you need to enter (in mysql_example/mysql.cnf)  
# Only necessary if you cannot connect to db by entering "mysql" 
# password=<your_root_pw> 
./setup.sh 
```
