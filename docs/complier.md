# complier


```shell

odb -d mysql --generate-schema person.hxx
odb -d mysql --generate-schema --generate-query --default-pointer std::tr1::shared_ptr --generate-session employee.hxx

```

```shell

g++ -c person-odb.cxx
g++ -DDATABASE_MYSQL -c driver.cxx
g++ -o driver driver.o person-odb.o -lodb-mysql -lodb
```


```shell
scp person.sql root@60.205.225.118:~
scp employee.sql root@60.205.225.118:~
ssh root@60.205.225.118

mysql --user=root --password=5Edidada --database=odb_test < person.sql
mysql --user=root --password=5Edidada --database=odb_test < employee.sql

./driver --user root --password 5Edidada --database odb_test --host 60.205.225.118
```

执行结果

```shell

testodbcomposite --user root --password 5Edidada --database odb_test --host 60.205.225.118
Mr Joe Dirt <joe@example.com>
  nickname: Squeaky
  alias: Anthony Clean
  phone 1: 555 5555
  phone 2: 666 6666
Mr Joe Dirt

```
