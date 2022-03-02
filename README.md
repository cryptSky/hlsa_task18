# How to install and run the application

1. Clone the repository `git clone https://qonand@bitbucket.org/qonand/homework18.git`
2. Run `./build.sh` in the project folder

# How to test replication
1. Login to the master container with help the command `docker-compose exec mysql_master bash`
2. Login to mysql server with help the command `mysql -u root -p` and enter password `111`
3. Select the database with help the command `USE mydb;`
4. Create a table 
```
CREATE TABLE users (
    id INTEGER(11) UNSIGNED AUTO_INCREMENT NOT NULL,
    login VARCHAR(255),
    password VARCHAR(255),
    name VARCHAR(255),
    created_at DATETIME,
    PRIMARY KEY (id),
    UNIQUE (login)
);

```
5. Run query to test replication, for example `INSERT INTO users (login, password, name, created_at) VALUES ('test-login', 'test-password', 'test-name', NOW());`
