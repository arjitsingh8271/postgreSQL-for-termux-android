# postgreSQL-for-termux-android


## Install Termux: 
* Google PlayStore: https://play.google.com/store/apps/details?id=com.termux
* Fdroid PlayStore(Recommended): https://f-droid.org/en/packages/com.termux
* Github (latest builds): https://github.com/termux/termux-app/releases

Once termux is installed open it and use the shell for below commands

* ### Install PostgreSQL:
```bash
apt update && apt install postgresql
```


* ### Create directory and initialize PostgreSQL Database Cluster:
```bash
mkdir ./postgres && initdb ./postgres
```
this directory stores all the postgresql data and setting files.

* ### Start the PostgreSQL Database Server:
```bash
pg_ctl -D ./postgres start
```

* ### Login/Quit to Postgres Shell:
```bash
# Login:
psql -d postgres

# Quit:
\q
```

* ### Stop PostgreSQL Database Server:
```bash
pg_ctl -D ./postgres stop
```

* ### Other:

You can optionally create aliases to start and stop the DB server and put them in your .bashrc/.zshrc files:
```bash
alias pgstart='pg_ctl -D ./postgres start' >> ~/.bashrc
alias pgstop='pg_ctl -D ./postgres stop' >> ~/.bashrc
```
Then use this aliases `pgstart` to start the Postgres Server 
& `pgstop` to stop the Postgres Server.

You can additionally create the more databases and DB users directly from bash shell:
```bash

# Creating additonal DB:
createdb db_name

# Creating additional DB user:
createuser --superuser --pwprompt pg_user
```







