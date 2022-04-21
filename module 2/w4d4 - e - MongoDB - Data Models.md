
# MongoDB - Data Models

<!--

Status: draft

@todo: define detailed examples

-->


## Intro:

- in our documents, we may need to store more complex data (eg. object)
  - explain with an object.

- relationships between data:
  - Embedded documents
  - References

- How to implement this with Mongoose (at the end of this document)


- Examples with an e-commerce app:
  - Product + specs(size, weight,...) (1:1)
  - Product + comments (1:many with embedded documents)
  - Product + Seller (1:many with references)
    - opt1: store ref. in the seller (need to keep an array)
    - opt2: store ref. in the product (easier)
    - opt3: store ref. in both models (problem: single source of truth, easier to corrupt DB)
  - (bonus) Each product can have multiple sellers (many:many with references)
    - store [ref.] in the seller (easier to get list of products from seller)
    - store [ref.] in the product (easier to get list of sellers of a product)


## CHEATSHEET

https://gist.github.com/sandrabosk/b5924056a33b82de3bb55a7457db741d




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

- If we use a reference, every time we need to retrieve the datawe'll need to make multiple queries to resolve the reference.

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

```
    const bookSchema = new mongoose.Schema({
        title: String,
        author: {type: mongoose.Schema.Types.ObjectId, ref: 'Author'}, //single reference
        author: [ {type: mongoose.Schema.Types.ObjectId, ref: 'Author'} ] //multiple
    });
```


- Embed documents (source: https://mongoosejs.com/docs/subdocs.html):

    ```
    const parentSchema = new Schema({
        children: [childSchema], // Array of subdocuments
        child: childSchema // Single nested subdocuments
    });
    ```



