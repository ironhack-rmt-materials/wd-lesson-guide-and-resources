

# mongoose - DeprecationWarning strictQuery option




## Problem

When I run my app, I get this in the terminal:

>  [MONGOOSE] DeprecationWarning: Mongoose: the strictQuery option will be switched back to false by default in Mongoose 7. Use mongoose.set('strictQuery', false); if you want to prepare for this change. Or use mongoose.set('strictQuery', true); to suppress this warning.



## Explanation

- `strictQuery` is an option that controls how query filters handle fields that are not defined in the schema.

- The default value has changed in different versions of mongoose (in version 6, they decided to make it true by default but it was creating a lot of confusion, so in version 7 they decided to switch it back to false)


More details:
- ![strictQuery explanation](../../../media/images/mongoose%20-%20strictQuery%20explanation.png)



## How to turn off this warning

- you can add `mongoose.set('strictQuery', false);` after you require mongoose (by setting that to false, we make sure that it is in line with most versions of mongoose, including the latest version)


Example:
- ![strictQuery configuration example](../../../media/images/mongoose%20-%20strictQuery%20configuration.png)


