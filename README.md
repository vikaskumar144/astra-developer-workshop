# astra-developer-workshop

## Use Case 


## Create keyspace and database
`DESCRIBE KEYSPACE;`

`CREATE KEYSPACE mytestapp WITH REPLICATION = { 'class' : 'org.apache.cassandra.locator.NetworkTopologyStrategy', 'dc-1': '1' } AND DURABLE_WRITES = true;`

`use mytestapp;`

#### Create table users_by_city
`CREATE TABLE IF NOT EXISTS users_by_city ( 
	userid uuid,
	first_name text,
	last_name text,
	email text,
	city text,
	address text,
	PRIMARY KEY ((city), email, userid));`

  
#### Insert some test data
`INSERT INTO users_by_city (userid, first_name, last_name, email, city, address)
VALUES (now(), 'vikas', 'kumar', 'vikas@demo.com', 'delhi', '110092');`

`INSERT INTO users_by_city (userid, first_name, last_name, email, city, address)
VALUES (now(), 'rahul', 'singh', 'rahul@demo.com', 'mumbai', 'andheri east');`

#### Fetch data from table 
`SELECT * from users_by_city;`

```
city   | email          | userid                               | address      | first_name | last_name
--------+----------------+--------------------------------------+--------------+------------+-----------
  delhi | vikas@demo.com | dfbea2b0-048b-11eb-8d4b-e7907aa277e7 |       110092 |      vikas |     kumar
 mumbai | rahul@demo.com | 029bf580-048c-11eb-8d4b-e7907aa277e7 | andheri east |      rahul |     singh
 
 ```
 
#### Create table product

`CREATE TABLE IF NOT EXISTS products (
    productid uuid,
    product_name text,
    product_category text,
    product_description text,
    PRIMARY KEY ((product_category), productid));`
    
#### Insert some random data 

`INSERT INTO products (productid, product_name, product_category, product_description)
VALUES (now(), 'monitor', 'computer', 'HP 32 inch FHD monitor');`

`INSERT INTO products (productid, product_name, product_category, product_description)
VALUES (now(), 'Keyboard', 'computer accessories', 'Dell US full keyboard');`

`INSERT INTO products (productid, product_name, product_category, product_description)
VALUES (now(), 'iphone 11', 'mobile', 'iphone 11 black color witrh 128 GB internal storage');`


#### Fetch data from table 
```
product_category     | productid                            | product_description                                 | product_name
----------------------+--------------------------------------+-----------------------------------------------------+--------------
             computer | 55155d30-048f-11eb-8d4b-e7907aa277e7 |                              HP 32 inch FHD monitor |      monitor
               mobile | a8354570-048f-11eb-8d4b-e7907aa277e7 | iphone 11 black color witrh 128 GB internal storage |    iphone 11
 computer accessories | 75eea2a0-048f-11eb-8d4b-e7907aa277e7 |                               Dell US full keyboard |     Keyboard
```
