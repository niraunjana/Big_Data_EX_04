# Big_Data_EX_04

# EX_04 - Implement NoSQL Database Operations: CRUD Operations and Arrays using MongoDB

## Aim:

To perform basic CRUD (Create, Read, Update, Delete) operations and manipulate array data types in a MongoDB collection.

## Requirements:

1. MongoDB installed and running locally or MongoDB Atlas account

2. MongoDB shell (mongosh) or MongoDB Compass GUI or MongoDB driver for Python/Node.js

3. Basic understanding of MongoDB documents and collections

## Algorithm:

1. Create: Insert single or multiple documents into a collection using insertOne() and insertMany().

2. Read: Retrieve documents from the collection using find() with optional filters.

3. Update: Modify existing documents using updateOne(), updateMany(), or replaceOne().

4. Delete: Remove documents using deleteOne() or deleteMany().

5. Arrays: Store and manipulate array fields inside documents.

## Program:
```
DEVELOPED BY : NIRAUNJANA GAYATHRI G R
REGISTER NO. : 212222230096
```
```
// Use the MongoDB shell or a MongoDB driver

// 1. Create Operations
// Insert one document
db.student.insertOne({
  name: "Sumit",
  age: 22,
  courses: ["Math", "Physics", "Chemistry"],
  year: 3
});

// Insert many documents
db.student.insertMany([
  {
    name: "Anita",
    age: 20,
    courses: ["Biology", "Chemistry"],
    year: 2
  },
  {
    name: "Rahul",
    age: 23,
    courses: ["History", "English"],
    year: 4
  }
]);

// 2. Read Operations
// Retrieve all documents
db.student.find().pretty();

// Retrieve students older than 21
db.student.find({ age: { $gt: 21 } }).pretty();

// 3. Update Operations
// Update age of Sumit to 23
db.student.updateOne(
  { name: "Sumit" },
  { $set: { age: 23 } }
);

// Add a course to Anita's course array
db.student.updateOne(
  { name: "Anita" },
  { $push: { courses: "Computer Science" } }
);

// Update year to 4 for all students in year 3
db.student.updateMany(
  { year: 3 },
  { $set: { year: 4 } }
);

// 4. Delete Operations
// Delete student Rahul
db.student.deleteOne({ name: "Rahul" });

// Delete all students younger than 21
db.student.deleteMany({ age: { $lt: 21 } });

```

## Output:

![image](https://github.com/user-attachments/assets/1007dc9d-0ae0-49eb-8761-74492765a939)

![image](https://github.com/user-attachments/assets/aacff738-b462-4617-862c-9641cd7e8345)

![image](https://github.com/user-attachments/assets/c37ebb4a-d04f-4ec8-a32f-605f1fa6dbc6)

![image](https://github.com/user-attachments/assets/d6db7ccd-7193-4b56-8265-1c5a35b35729)


## Result:

The CRUD operations in MongoDB were successfully performed. Documents were created with array fields, read with filters, updated (including array manipulation), and deleted based on specified criteria. MongoDB’s flexible schema and array support enable effective management of NoSQL data.

