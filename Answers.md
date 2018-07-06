# Describe the following: `DataBase`, `Collection` , `Document`

    Database - A physical storage of data that is organized in such a way that the data is easily accessible, maintainable, and generally fast to query. A database is specialized to the data it holds.

    Collection - A 'collection' or group of documents within a database which are related.

    Document - The short answer is data. The longer answer is documents are JSON Objects with field:value pairs, consisting of BSON data types. MongoDB has constraints (rules) on field naming, mostly notably that '_id' is a reserved field name only to use as a Primary Key.

# Describe how one can achieve the pattern of _relationships_ in MongoDB. What needs to take place at the schema level? How do we _'fill'_ in the appropriate relational data using mongoose?

    Since MongoDB is a tables-less database, relationships are achieved through the populate method using the ref keyword. Ref populates a field in the schema with an array of documents from the specified Model. 
    
    An example of its usage:

    ```
    friends: [{ type: Schema.Types.ObjectId, ref: 'Friends' }]
    ```

# Explain a way to break up an API into Sub-Applications, which tool did we use to do that?

    We used Mongoose to break up the API into sub-applications. Mongoose makes it easier to access CRUD operations and MongoDB commands. It also helps us shape our data using schemas and models. Schemas allow us to add constraints and add fields to our documents. Models are like the blueprints of documents. We were able to break up the API using these schemas and models. For instance, I have 3 directories and each holds a Schema and Model definition as well as their respective CRUD endpoints. This organization makes it easy to make changes or look through the code.