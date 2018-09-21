
# DynamoDB

* NoSQL fully managed database service
* Dynamo db stores 3 geographically distinct replicas of each table
* tables can have any amount of data, you need to manage throughput
* remains available when scaling up or scaling down
* no need for user to partition, as it is fully managed service
* can scale read/write capacity up/down without any downtime
* performance is controlled through provisioned throughput
* all data is stored on SSD
* Synchronous replication across availability zones
* strong consistency and atomic counters available
* holds structured data with low latency read writes to items ranging from 1 byte to 400kb; whereas s3 stores unstructured data upto 5tb
* dynamodb can be used by applications running on any operating system
* Dynamodb local is an offline version of dynamo db
* supports key-value and document data structure
* key-value store is normal key-value store that I know about
* document store you can store query update documents formats like json, xml, html
* dynamodb does not have json data type, but you can pass json. Dynamob datatypes are superset of json

## DynamoDB data model

* table : collection of data items, can have unlimited data items
* item : is composed of a primary key, composite key and flexible number of attributes. can have unlimited number of attributes, but total item size should be from 1 byte to 400kb
* attribute: has attribute name and value or set of values. Individual attributes have no size restriction, but total item size should be less than 400kb


## Dynamo DB Limits

* no limit on how much data and throughput
* 256 tables per region, can increase by calling aws
* range primary key can have 1024 bytes
* hash primary key can have 2048 bytes
* item size - one row in table 400kb including attribute name
* 5 local and 5 global secondary indexes per table

## Keys

* primary key is the only required attribute
* you specify primary key when you create a table
* primary key can be hash index ; or hash and a range key composite
* primary key should be unique for good performance; eg userid for user table


## Secondary index

* upto 5 Local Secondary Index: same Id as primary hash, but different range
* It is local because the scope stays to the same hash key partition as the table
* upto 5 global secondary index: hash and rage key are different to that of table, hence queries can span all data in the table across all partitions

## Local secondary index

* Local Secondary index can be added only at the time of table creation. They cannot be added or changed later
* You can specify the indexed range key and projection ie the subset of attributes to be returned
* LSI supports both strong and eventually consistent read
* the primary index of the table must use a hash-range composite key
* there can be upto 20 projected non-key attribues

## Item Collection

* A group of items having the same hash key is an item collection. Similar to shards or partitions in normal sql
* Item collection max size is 10GB
* Item collections are automatically created and maintained for tables having local secondary index

## Global Secondary Index

* Global secondary index can be specified at any time, they can be changed even after table creation
* global secondary index need not be on unique attribute, unlike primary key
* Global secondary index support eventual consistency only
* you can provision throughput for table and each associated global secondary index at the time of table creation

## Provisioned throughput

* each table can have read write throughput provisioned. based on provisioning, in the background aws assigns resources
* Unit of read capacity: 1 strongly consistent read per second of 4kb item
* 2 eventually consistent read per second of 4kb item
* Unit of write capacity: 1 write per second of 1kb item
* if you want to have read/write throughput of more than 10000 per table, then contact AWS
* if you want to have more than 20000 read/write per aws account, then contact AWS
* minimum throughput is 1 for read/write
* you can increase throughput any number of time. increasing throughput takes few minutes to few hours
* you can decrease throughput only 4 times in a day. takes few seconds to few minutes
* if more read/write than provisioned then they will be throttled and you will get 400 error code. You can monitor throughput in cloud watch

## Reserved capacity

* you can reserve capacity by upfront payment and a commitment of minimum monthly usage
* You cannot cancel reserved capacity
* smallest reserved capacity is 100 reads/writes
* cannot move reserved capacity to another region

## Query

* supports get/put operations using user defined primary key
* Supports conditional operations
* supports increment and decrement operations
* search only primary and secondary keys
* more efficient
* returns all attributed of an item, but projection expression can be created to return fewer attributes
* by default it is eventually consistent, can change to strongly consistent

## Scan

* reads every item in the table, and applies filter to refine results
* will scan all items/ attributes in the table
* inefficient and slower performance
* Only eventually consistent reads are available
* Scan has limit of 1MB per operation. LastEvaulatedKey is returned to pickup next set of data

## Conditional Writes and atomic counters

* multiple users updating item at the same time. Conditional write only updates the item if a condition is met
atomic counter allows you to increment or decrement a value of an existing attribute without interfering with other write requests
* atomic: all writes are applied in the order received
* Use UpdateItem for atomic coutner inc/dec
* atomic update is fast in place update

## Dynamo DB strongly vs eventually consistent

* when reading data, user can specify if they want eventual or strongly consistent read
* eventually consistent is default consistency is usually reached within 1 second
* strongly used extra read throughput capacity to ensure that you receive most upto date version of an item

## Common API commands

* BatchGetItem to get many items at time through API. Not BatchGetItems
* BatchWriteItem, PutItem
* CreateTable, DeleteTable, UpdateTable, DescribeTable, ListTables
* UpdateItem
* ProjectionExpressions can be defined to determine which attributes are returned form a table
