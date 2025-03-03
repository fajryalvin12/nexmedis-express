# 2. Design indexing strategy for optimizing Data

## a. fetch a user by username

```sql

-- select the whole column from table users
select * from users u

-- consider to the single table which have to fetch quickly, using the individual indexing for effective result. Due to the username column needs, the indexing take the "username" column for table users.
create index users_username_idx on users("username")

-- fetch the users from indexing
select users u from users_username_idx where username=$1
```

## b. fetch users who signed up after a certain date

```sql
select * from users u

create index users_cat_idx on users("created_at")

select * from users_cat_idx where created_at > "2023-01-01"
```

## c. fetch a user by email

```sql
select * from users u

create index users_email_idx on users("email")

select * from users_email_idx where email = $1

```
