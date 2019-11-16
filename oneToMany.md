# customer && orders . one to many relationship

1. one customer can do many orders. 

``` create database customers;  ```

 ```js
   create table customers( 
         id int auto_increment primary key,  
         first_name varchar(100), 
         last_name varchar(100),
          email varchar(100)
          );

```
```js
  insert into customers (first_name, last_name, email) 
                 values ('Boy', 'George', 'george@gmail.com'),
                        ('George', 'Michael', 'gm@gmail.com'),
                        ('David', 'Bowie', 'david@gmail.com'),
                        ('Blue', 'Steele', 'blue@gmail.com'),
                        ('Bettle', 'Davis', 'bettle@gmail.com');

```

```js
  create table orders( 
    id int auto_increment primary key,  
    order_date date,  amount decimal(8,2), 
    customer_id int, 
    foreign key(customer_id) references customers(id)
    );

```

```js
   insert into orders(order_date, amount, customer_id)
                values ('2016/02/10', 99.99, 1),
                      ('2017/11/11', 35.50, 1),
                      ('2014/12/12', 800.67, 2),
                      ('2015/01/03', 12.50, 2), 
                      ('1999/04/11', 450.25, 5);
```

```js
 SELECT * FROM customers WHERE last_name='George',
 SELECT * FROM orders WHERE customer_id = 1;
        combine 

 SELECT * FROM orders WHERE customer_id = (
   SELECT id FROM customers WHERE last_name='George'
     )

```

# cross join (useless)

```js
  SELECT * FROM customers, orders; 

```

# implicit inner join

```js
  SELECT * FROM customers, orders WHERE customers.id = customer_id; 

  SELECT first_name, last_name, order_date, amount
   FROM customers, orders WHERE customers.id = customer_id;

```

# explicit inner join

```js
 
  SELECT * FROM customer JOIN orders ON customers.id = customers_id; 

  SELECT first_name, last_name, order_date, amount FROM customers JOIN orders ON customers.id = customer_id;

```

1. Q: find the highest  spender  customer; 

```js
 SELECT first_name, last_name, SUM(amount) as TOTAL  FROM customers JOIN orders ON customers.id = customer_id GROUP BY orders.customer_id ORDER BY  3 DESC;
 ```