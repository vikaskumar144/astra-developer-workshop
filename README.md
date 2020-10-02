# astra-developer-workshop

## Use Case 


## Create keyspace and database
`DESCRIBE KEYSPACE;`
`CREATE KEYSPACE mytestapp WITH REPLICATION = { 'class' : 'org.apache.cassandra.locator.NetworkTopologyStrategy', 'dc-1': '1' } AND DURABLE_WRITES = true;`
