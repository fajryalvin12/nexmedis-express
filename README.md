# 1. Create RESTful endpoints, HTTP Methods, URL Structure, Response Format

## a. User Registration and authentication

- Endpoint : "/signup" (registration), "/login"(authentication)
- HTTP Method : POST
- URL Structure : http://localhost:3000/signup (registration)
  http://localhost:3000/login (authentication)
- Response format :
  // Registration
  ```javascript
  {
  status : 200,
  message : "Success created the account",
  data : {
    email : "user@gmail.com",
    username : "User"
  }
  }
  // Authentication
  {
  status : 200,
  message : "Success created the account",
  data : {
    email : "user@gmail.com",
    username : "User"
  }
  }
  ```

## b. Viewing and Searching Products

- Endpoint : "/products" (viewing products), "/search=productName" (searching products)
- HTTP Method : GET
- URL Structure : http://localhost:3000/products (viewing products)
  http://localhost:3000/search=productName (searching products)
- Response format :
  ```javascript
  // Viewing Products
  {
  status : 200,
  message : "List Products",
  data : [
  {
    id : 1,
    name : "Product A",
    price : 90000,
    qty : 45
  },
  {
    id : 2,
    name : "Product B",
    price : 80000,
    qty : 23
  },
  {
    id : 3,
    name : "Product C",
    price : 75000,
    qty : 12
  },
  ]
  }
  // Searching Products
  {
  status : 200,
  message : "Success find the products",
  data :
  {
    id : 3,
    name : "Product C",
    price : 75000,
    qty : 12
  },
  }
  ```

## c. Adding Items to a shopping cart

- Endpoint : "/cart"
- HTTP Method : POST
- URL Structure : http://localhost:3000/cart
- Response format :

```javascript
  {
  status : 200,
  message : "Add the product to the cart",
  data :
  {
    id : 3,
    name : "Product C",
    price : 75000,
    qty : 12
  },
  }
  // User did not authenticate the account
  {
    status : 401,
    message : "Unauthorized"
  }
```

## d. Completing a purchase

- Endpoint : "/transaction"
- HTTP Method : POST
- URL Structure : http://localhost:3000/transaction/
- Response format :

```javascript
  {
  status : 200,
  message : "Success buy the product",
  data :
  {
    id : 3,
    name : "Product C",
    price : 75000,
    qty : 12
  },
  }
```
