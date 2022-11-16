

# e-commerce platform as project2



## Example

https://redid.herokuapp.com/
https://github.com/Haridha-Serhii-website/ecommerce-project



This is the planning we were doing....


Models:
- User
- Product
- Order ?


MVP - Option 1:
- sellers can C+U+D products
- buyers can buy


MVP - Option 2 (Marketplace)
- any user can R products
- any logged in user can C+U+D products
- only owner can U+D


MVP - Option 3:
- User model -- CR
- Product model -- data added with a seed file
- Order model -- CRUD
  - product: ref. Product
  - quantity: Number
  - totalPrice: Number
  - address

- Simplification: a user can buy only one product (can choose quantity)
  - this is important, so that they don't need to keep a shopping cart.


Bonus:
- only owner can UD orders
- responsive 
- images
- payment gateway 
- send email when user places an order
- shopping cart (users can place an order with multiple products)



## Final project e-commerce example (online payments with Stripe)

- url: https://mai-baby.netlify.app/
- server: https://github.com/mai-baby/mai-baby-server
  - in package.json, you'll see he used a package "stripe"
- client: https://github.com/mai-baby/mai-baby-client


