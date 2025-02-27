# 1. Create RESTful endpoints, HTTP Methods, URL Structure, Response Format

## a. User Registration

- Endpoint : "/signup"
- HTTP Method : POST
- URL Structure : http://localhost:3000/signup
- Request Body :

```javascript
{
    fullname : "User_1",
    email : "user@gmail.com",
    password : "12345678",
    confirmPassword : "12345678"
}
```

- Response format :
  ```javascript
  {
    status : 200,
    message : "Success created the account",
    data :
    {
      email : "user@gmail.com",
      username : "User"
    }
  }
  ```

## b. User authentication

- Endpoint : "/login"
- HTTP Method : POST
- URL Structure : http://localhost:3000/login
- Request Body :

```javascript
{
    email : "user@gmail.com",
    password : "12345678",
}
```

- Response format :
  ```javascript
  {
    status : 200,
    message : "Login Success"
  }
  ```

## c. Viewing Products

- Endpoint : "/products"
- HTTP Method : GET
- URL Structure : http://localhost:3000/products
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
  ```

## d. Searching Products

- Endpoint : "/search=productName"
- HTTP Method : GET
- URL Structure : http://localhost:3000/search=productName
- Response format :
  ```javascript
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

## e. Adding Items to a shopping cart

- Endpoint : "/cart"
- HTTP Method : POST
- URL Structure : http://localhost:3000/cart
- Request Body :

```javascript
{
    id: 3,
    name : "Product C",
    price : 75000,
    qty : 1
}
```

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
        qty : 1
    },
  }
  // User did not authenticate the account
  {
    status : 401,
    message : "Unauthorized"
  }
```

## f. Completing a purchase

- Endpoint : "/transaction/:id"
- HTTP Method : POST
- URL Structure : http://localhost:3000/transaction/:id
- Request Body :

```javascript
    {
        productId : 3,
        name : "Product C",
        price : 75000,
        qty : 1,
        paymentMethod : "Bank Transfer"
        userId: 1,
    },
```

- Response format :

```javascript
  {
    status : 200,
    message : "Success buy the product",
    data :
    {
        transactionId : 1,
        productId : 3,
        name : "Product C",
        price : 75000,
        qty : 12,
        paymentMethod : "Bank Transfer",
        userId : 1
    },
  }
```

# 2. Design indexing strategy for optimizing Data

## a. fetch a user by username

```sql
SELECT * FROM USERS

CREATE INDEX USER_IDX ON USERS("username")
```

## b. fetch users who signed up after a certain date

```sql
SELECT * FROM USERS

CREATE INDEX USER_IDX ON USERS("created_at")
```

## c. fetch a user by email

```sql
SELECT * FROM USERS

CREATE INDEX USER_IDX ON USERS("email")
```
