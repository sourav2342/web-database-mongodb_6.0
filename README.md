# web-database-mongodb_6.0

INSTALLING MONGODB 6.0:

https://medium.com/@LondonAppBrewery/how-to-download-install-mongodb-on-windows-4ee4b3493514

this link provides the installation steps for downloading mongodb but as of 2020 the installation steps have been changed the latest vers now is mongodb 6.0.

After version 6.0.0 mongo.exe does not get installed to your bin folder so you have to manually install the new MongoDB shell which is called mongosh then you have to
add its path to your system variables and then run mongosh --version to see if it got installed. 

It should be noted, that in MongoDB version 6.0 there are two items:

The legacy mongo shell is removed from MongoDB 6.0

The MongoDB Shell (mongosh) is not installed with MongoDB Server. You need to follow the mongosh installation instructions to download and install mongosh separately. This was already announced in MongoDB version 5.0

The legacy mongo shell does not exist anymore on MongoDB version 6.0. If you desire the old mongo.exe, then you can install if from an earlier MongoDB version.

the link to the installation process:https://medium.com/@nischandra/install-mongodb-6-0-in-windows-11-2022-5d6d5e748323
resoures link:https://stackoverflow.com/questions/73081708/mongo-exe-not-installed-in-version-6-0-0/75774152#75774152

RUNNING MONGODB:

      mongod and mongosh are both components of MongoDB, but they serve different purposes:

      mongod is the primary daemon process for the MongoDB server. It is responsible for managing the database's data files, handling client requests, and performing        other server-side operations.

      mongosh is the MongoDB shell, which is a command-line interface for interacting with MongoDB. It provides a JavaScript interface for managing MongoDB databases,      collections, and documents.

      //"It is important to run mongod before running mongosh because mongosh needs to connect to a running MongoDB server in order to interact with the database". The           mongod daemon process is responsible for managing the database's data files and handling client requests, so it needs to be running in order for mongosh to             connect to it.

      When you start the mongod process, it creates a MongoDB server instance that listens for client connections on a default port (27017). Once the server is               running, you can connect to it using the mongosh shell or other MongoDB client tools.

create DBs:
    
    show dbs: gives list of databases by default at start there are three dbs.
    db:show current working db.
    use [name_of_db]:
     to create a new database cmd: use [name_of_db] // by using this cmd (mongosh shell) msongodb        tell that we have switched to database [nam__].
     show dbs: doen't show db created unless some content is created in it.
     
     
 


CRUD OPERATIONS:
  
 
  
  Collections
      MongoDB stores documents in collections. Collections are analogous to tables in relational           databases.

      Create a Collection
      If a collection does not exist, MongoDB creates the collection when you first store data for         that collection.

      db.myNewCollection2.insertOne( { x: 1 } )
      db.myNewCollection3.createIndex( { y: 1 } )

      Both the insertOne() and the createIndex() operations create their respective collection if          they do not already exist. Be sure that the collection name follows         MongoDB Naming         Restrictions.

      Explicit Creation
      MongoDB provides the db.createCollection() method to explicitly create a collection with             various options, such as setting the maximum size or the documentation     
      validation rules. If you are not specifying these options, you do not need to explicitly             create the collection since MongoDB creates new collections when you 
      first store data for the collections.
      
      adding collection to database db.collection.insertOne({_id:1,value:45,price:"65"})
      
      db.products.insertMany( [
      { _id: 10, item: "large box", qty: 20 },
      { _id: 11, item: "small box", qty: 55 },
      { _id: 12, item: "medium box", qty: 30 }
      ] );
      
      LINK:https://www.mongodb.com/docs/manual/core/databases-and-collections/#std-label-collections
      
      show collections: to show the different collections in the db.
      products is called as collection which contains collection od documents.
      
      
      READING AND QUERIYING:
      
        read operation:
            
            db.collection.find()
            ex: db.products.find({
              {qty:{$gt:20}}  qty>20
              {_id:}
            })
        https://www.mongodb.com/docs/mongodb-shell/crud/read/  
            
      UPDATE:
         
          db.product.updateOne( 
          {_id:1}, 
          {$set:{{name:'parker', price:60}}}
          )
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
