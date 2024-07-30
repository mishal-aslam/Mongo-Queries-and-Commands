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
db.collectionName.insertOne({ name: "mishal" , age: 20 , profession: "frontend dev"  })
```

## Insert Multiple Rows

```
db.collectionName.insertMany([
  {
    name: "Mishal",
    age: 20,
    profession: "Frontend Developer"
  },
  {
    name: "John Doe",
    age: 22,
    profession: "Full Stack Developer"
  }
])
```

## Get all Rows

```
db.collectionName.find()
```

## Search for specific row in a database

```
db.collectionName.findOne({ name :"mishal"  })
```

## Filter Data

```
db.collectionName.find({ age: 20 })  // Find documents with age 20
db.collectionName.find({ profession: "frontend dev" })  // Find documents with profession "frontend dev"
```

## Retrieving Specific Fields from a Collection

```
db.collectionName.find({}, { name: 1, age: 1, _id: 0 })  // 1 for true  and 0 for false
```
```
db.collectionName.find({ profession: "front end dev" }, { name: 1, age: 1, _id: 0 })
```

## Sort Data

```
db.collectionName.find().sort({ age: 1 })  // Sort documents by age in ascending order
db.collectionName.find().sort({ age: -1 })  // Sort documents by age in descending order
```

## Limit Data

```
db.collectionName.find().limit(2)  // Limit the result to 2 documents
```

## Update Specific Data in a Database

```
 db.collectionName.updateOne({ name: "mishal"}  , { $set : {name: "mishal aslam" }} )
```

## Update Multiple Documents

```
db.collectionName.updateMany({ profession: "frontend dev" }, { $set: { profession: "front-end dev" } })
```

## delete Specific Data in a Database

```
 db.collectionName.deleteOne({ name: "mishal aslam"  })
```

## Delete Multiple Documents

```
db.collectionName.deleteMany({ age: { $gt: 25 } })  // Delete documents with age greater than 25
```

## Drop a Collection in MongoDB

```
 db.collectionName.drop()
```

## Remove the entire database.

```
 db.dropDatabase()
```


## Greater Than Less Than and or equal

```
db.collectionName.find({age: {$gt:20}})  // greater than
db.collectionName.find({age: {$lt:25}})  // less than
db.collectionName.find({age: {$gte:21}})  //greater than or equal
db.collectionName.find({age: {$lte:25}})  //less than or equal
```


## Query for a Document Nested in an Array

```
db.books.insertMany([
  {
    "title": "Book Title",
    "author": "Author Name",
    "pageCount": 250,
    "genres": ["Fiction", "Thriller", "Mystery"],
    "reviews": [
      {
        "reviewerName": "John Doe",
        "rating": 4,
        "reviewText": "Great book!"
      },
      {
        "reviewerName": "Jane Smith",
        "rating": 5,
        "reviewText": "Excellent read!"
      }
    ]
  },
  {
    "title": "Another Book Title",
    "author": "Another Author Name",
    "pageCount": 300,
    "genres": ["Non-Fiction", "Biography", "History"],
    "reviews": [
      {
        "reviewerName": "Alice Brown",
        "rating": 4,
        "reviewText": "Informative and engaging."
      }
    ]
  }
])
```

## To find documents where "Fantasy" is the only value in the "genres" array, you can use the $eq operator:

```
db.books.find({ genres: { $eq: ["Fantasy"] } })
```

## To find documents where "Fantasy" is one of the values in the "genres" array, you can use the $in operator:

```
db.books.find({ genres: { $in: ["Fantasy"] } })
```

## finding ratings within an array of objects (reviews)

```
db.books.find(
  {"reviews.rating" : 3}
)
```

```
db.books.find(
  { reviews: { $elemMatch: { rating: 5 } } },
  { "reviews.rating": 1  , "genres" : 1 , "_id": 0}
)
```


