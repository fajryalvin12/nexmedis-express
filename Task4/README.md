# 4. Optimizing the SQL Query

CREATE TABLE orders (
id INT PRIMARY KEY,
customer_id INT,
product_id INT,
order_date TIMESTAMP,
amount DECIMAL(10, 2)
);

\*) Assume that customer_id is indexed, but amount and order_date are not indexed.

## a. Find the top 5 customers who spent the most money in the past month.

```sql

select customer_id cu
from orders
where order_date < "2023-01-01"
order by amount desc
limit = 5

```

## b. How would you improve the performance of this query in a production environment?

- choose the neccesary column to fetch
- avoid using asterix (\*) for fetching the data in the column
- use indexing to make queries more effective
- use explain and analyze to check the query performance gradually
