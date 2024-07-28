# MongoDb-Queries

## Show all Database

```
show dbs 
```

## Create database and insert it in the server

```
use databaseName
```

## Insert Field into the collection

```
db.databaseName.insertOne({ name: "mishal" , age: 20 , proffesion: "frontend dev"  })
```

## Way to search for data in a database

```
db.databaseName.find()
```

## Way to search for specific data in a database

```
db.databaseName.findOne({ name :"mishal"  })
```

## Update Specific Data in a Database

```
 db.databaseName.updateOne({ name: "mishal"}  , { $set : {name: "mishal aslam" , gender: "female"  }} )
```

## delete Specific Data in a Database

```
 db.databaseName.deleteOne({ name: "mishal aslam"  })
```

## Drop a Collection in MongoDB

```
 db.databaseName.drop()
```

## Remove the entire database.

```
 db.dropDatabase()
```







