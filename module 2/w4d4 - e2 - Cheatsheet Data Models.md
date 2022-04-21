

# Cheatsheet Data Models



## 1:1 relationships (use Embedded Documents)

    ```
    const addressSchema = new Schema({
        city: String,
        postCode: String
    });

    const companySchema = new Schema({
        name: String,
        numberOfEmployees: Number,
        address: addressSchema
    });
    ```


        
##  1:many relationships: option A, use Embedded Documents if possible (not duplicating data & limited data size)

    ```
    const addressSchema = new Schema({
        city: String,
        postCode: String
    });

    const companySchema = new Schema({
        name: String,
        numberOfEmployees: Number,
        address: [addressSchema]
    });
    ```


## 1:many relationships: option B, Reference

    ```
    const companySchema = new Schema({
        name: String,
        numberOfEmployees: Number,
        address: {type: mongoose.Schema.Types.ObjectId, ref: 'Address'}
    });

    ```


## many:many relationships, Reference

    ```
    const companySchema = new Schema({
        name: String,
        numberOfEmployees: Number,
        address: [{type: mongoose.Schema.Types.ObjectId, ref: 'Address'}]
    });
    ```



