# Amazon Aurora Multi-Master

```
sudo apt-get install mysql-client
sudo apt install python3-pip
pip3 install mysql-connector-python
```

```
HOST=<mysql host here>
MYSQL_PWD=cloudacademy mysql -h $HOST -u admin demo
```

```
select @@hostname;
```

```
CREATE DATABASE demo;
```

```
CREATE TABLE course (
    title VARCHAR(40), 
    instructor VARCHAR(40),
    duration INT, 
    created DATE, 
    url VARCHAR(256)
);
```

```
INSERT INTO course (title, instructor, duration, created, url) VALUES ('Course1', 'Jeremy Cook', 100, '1999-03-30', 'http://here.com');
```

```
AURORA_NODE1=<aurora endpoint 1 here>
AURORA_NODE2=<aurora endpoint 2 here>

watch -n1 "MYSQL_PWD=cloudacademy mysql -h $AURORA_NODE1 -u admin demo -e 'select count(*) from course'"
```

```
AURORA_NODE1=<aurora endpoint 1 here>
AURORA_NODE2=<aurora endpoint 2 here>

MYSQL_PWD=cloudacademy mysql -h $AURORA_NODE1 -u admin -e 'ALTER SYSTEM CRASH'
```
