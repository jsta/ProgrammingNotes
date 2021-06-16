## Notes on PostgreSQL

## Installation

```shell
sudo apt-get install postgresql
```

## Usage


### Command line

```shell
# List users
psql
\du

# Create a new database
createdb tempdb

```

<!-- To start postgres once:
  postgres -D /usr/local/var/postgres -->

<!-- Then connect with

  psql -d tempdb -->


### R RPostgreSQL package

```r
library(DBI)
library(RPostgreSQL)
drv <- dbDriver("PostgreSQL")
con <- dbConnect(drv, dbname="tempdb", host="localhost")
summary(con)

dbWriteTable(con, "mtcars", mtcars)

dbListTables(con)

rs <- dbSendQuery(con, "select * from mtcars")
fetch(rs) # grab everything (default n=-1)

rs <- dbSendQuery(con, "select * from mtcars")
fetch(rs, n=5) # grab 5 rows
fetch(rs) # grab the rest

rs <- dbSendQuery(con, "select * from mtcars where cyl =4")
x <- fetch(rs)
dbDisconnect(con)


con <- dbConnect(drv, dbname="bpsimple", host="localhost") # db from Apress book

rs <- dbSendQuery(con, paste('SELECT customer.fname, customer.lname,',
                                     'count(orderinfo.orderinfo_id) AS "no. orders"',
                             'FROM orderinfo, customer',
                             'WHERE orderinfo.customer_id = customer.customer_id',
                             'GROUP BY customer.customer_id'))
fetch(rs)

dbDisconnect(con)
```

---

python: psycopg2

```python
# basic use
import psycopg2
con = psycopg2.connect("dbname='bpsimple' host='localhost'")
cur = con.cursor()
cur.execute("SELECT * from customer")
rows = cur.fetchall()
```

---

Dates

cast('2004-06-23' as date)

select * from orderinfo where date_placed > cast('2004-06-23' as date);
