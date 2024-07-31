
# MongoDB - Data Models

<!--

Status: old 

(I now follow "w5d2 - b2 - ALTERNATIVE Codealong")

-->


## Intro:

- in our documents, we may need to store more complex data (eg. object)
  - explain with an object.

- 3 types of relationship:
  - one-to-one
  - one-to-many
  - many-to-many


- relationships between data:
  - Embedded documents
  - References

- How to implement this with Mongoose (at the end of this document)


## CHEATSHEET

Cheatsheet Sandra: 
- https://gist.github.com/sandrabosk/b5924056a33b82de3bb55a7457db741d

Cheatsheet Luis: 
- https://gist.github.com/luisjunco/a507e9f15acb32620cf8a33fff0904b1




## Option 1: By Reference (aka normalized data model)

- The relations are associations between documents of different collections through their _id

- Example 1: https://i.imgur.com/GmBjx9W.png

- Example 2: company + address


## Option 2:  Embedding documents

- save the related document inside the main one

- Example 1: https://i.imgur.com/yrliwPP.png

- Example 2: company + address (embedded address)

- Notes: 
  - it is also possible to have Multiple Sub-documents
  - a document in Mongo cannot be more than 16Mb in size


## Explain One-to-One vs One-to-Many relationships


## Data Model Examples and Patterns

- Useful link (Mongo DB documentation): 
  https://docs.mongodb.com/manual/applications/data-models-relationships/



## Example 1: Model One-to-One Relationships with Embedded Documents

- If we use a reference, every time we need to retrieve the data we'll need to make multiple queries to resolve the reference.

- Better approach: embedded document (we can get all the information with a single query)

- Example: company + address


## Example 2: Model One-to-Many Relationships with Embedded Documents

- (we can get all the information with a single query)

- Example: company + [address]


## Example 3: Model Many-to-Many Relationships with Document References

```
books: [id1, id2, ...]
```

- Example: companySchema + socialClubSchema + personSchema


## Example 4: Model Many-to-Many Relationships with intermediate References Collection

- In case our database structure leads to an unlimited number of elements (eg. books),  those arrays do have a dangerous long-term growth

- Solution: have an intermediary collection (each document in that collection storing the relationship between 2 documents).

- Example: company + [employee] (where a company can have unlimited number of employees)



## How do we implement all this in Mongoose

- Reference ()

  ```js
  const bookSchema = new mongoose.Schema({
      title: String,
      author: {type: mongoose.Schema.Types.ObjectId, ref: 'Author'}, //single reference
      authors: [ {type: mongoose.Schema.Types.ObjectId, ref: 'Author'} ] //multiple
  });
  ```


- Embed documents (source: https://mongoosejs.com/docs/subdocs.html):

    ```js
    const parentSchema = new Schema({
        child: childSchema // Single nested sub-documents
        children: [childSchema], // Array of sub-documents
    });
    ```



