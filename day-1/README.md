# Day 1

## Open mongo console
```shell
$ mongo
```

## Create database
```shell
> use nama_db
```

## Create collection/table
```shell
> db.createCollection('nama_table')
switched to db nama_db
```

## Insert data
```shell
> db.nama_table.insert({first: 'Alfian', last: 'Oktafireza'})
WriteResult({ "nInserted" : 1 })
> db.nama_table.insert({first: 'Ratna', last: 'Ariqoh'})
WriteResult({ "nInserted" : 1 })
```

## Get data

### All
```shell
> db.nama_table.find()
{ "_id" : ObjectId("6064287027892eb6451683a3"), "first" : "Alfian", "last" : "Oktafireza" }
{ "_id" : ObjectId("6064292c27892eb6451683a4"), "first" : "Ratna", "last" : "Ariqoh" }
>
> db.nama_table.find().pretty()
{
        "_id" : ObjectId("6064287027892eb6451683a3"),
        "first" : "Alfian",
        "last" : "Oktafireza"
}
{
        "_id" : ObjectId("6064292c27892eb6451683a4"),
        "first" : "Ratna",
        "last" : "Ariqoh"
}
```

### Specific

#### ID
```shell
> db.nama_table.find("6064292c27892eb6451683a4");
{ "_id" : ObjectId("6064292c27892eb6451683a4"), "first" : "Ratna", "last" : "Ariqoh" }
```

#### Object key
```shell
> db.nama_table.find({first: "Alfian"});
{ "_id" : ObjectId("6064287027892eb6451683a3"), "first" : "Alfian", "last" : "Oktafireza" }
```

## Update data
```shell
> db.nama_table.update({first: "Alfian"}, {$set: {last: "Oktafireza Syahputra"}});
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
```

## Delete data
```shell
> db.nama_table.remove({first: "Alfian"})
WriteResult({ "nRemoved" : 1 })
```

## Delete collection/table
```shell
> db.nama_table.drop()
true
```

## Delete database
```shell
> db.dropDatabase()
{ "dropped" : "nama_db", "ok" : 1 }
```