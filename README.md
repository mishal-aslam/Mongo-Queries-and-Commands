# MongoDb-Queries

## Show all Database

```
show dbs 
```

## Create and switch to database 

```
use collectionName
```

## Insert Row

```
db.collectionName.insertOne({ name: "mishal" , age: 20 , proffesion: "frontend dev"  })
```

## Insert Multiple Rows

```
db.collectionName.insertMany([{ name: "mishal" , age: 20 , profesion: "frontend dev"  } , { name: "john doe" , age : 22  , profession  : "full satck dev"  } ])
```

## Get all Rows

```
db.collectionName.find()
```

## Search for specific row in a database

```
db.collectionName.findOne({ name :"mishal"  })
```

## Update Specific Data in a Database

```
 db.collectionName.updateOne({ name: "mishal"}  , { $set : {name: "mishal aslam" }} )
```

## delete Specific Data in a Database

```
 db.collectionName.deleteOne({ name: "mishal aslam"  })
```

## Drop a Collection in MongoDB

```
 db.collectionName.drop()
```

## Remove the entire database.

```
 db.dropDatabase()
```







