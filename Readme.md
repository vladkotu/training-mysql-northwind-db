- [MySql northwind training db](#sec-1)
  - [Build/run instructions](#sec-1-1)

# MySql northwind training db<a id="sec-1"></a>

Based on [this project](https://code.google.com/archive/p/northwindextended/)

Differences from original project:

-   It's data only, no view table or stored procedures provided
-   All table names are snake cased

## Build/run instructions<a id="sec-1-1"></a>

Build image

```sh
docker build -t train-northwind .
```

Run container

```sh
docker run -d -p 3309:3306              \
       --name train-northwind           \
       -e MYSQL_ROOT_PASSWORD=rootpwd   \
       vladkotu/training-mysql-northwind-db
```

Connect throught cli

```sh
mysql -h 127.0.0.1 -P 3309 -uroot -prootpwd
```

```sql
SHOW DATABASES;
```

| Database                     |
|---------------------------- |
| information<sub>schema</sub> |
| mysql                        |
| northwind                    |
| performance<sub>schema</sub> |
| sys                          |
