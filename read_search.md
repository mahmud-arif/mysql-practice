# read data

1. SELECT * FROM <table_name>; 

2. SELECT <column_name> from <table_name>; 

   example from cats table

```js 
  SELECT name from cats 
```

3. SELECT <column_name> from <table_name> Where <logic>; 

     example

```js 
  SELECT * FROM cats WHERE age=4; 
```

4. alias set 

```js 
 SELECT cats_id as id FROM cats WHERE age=4; 
```


# Update 
 key word  UPDATE, SET , WHERE
 1. UPDATE <table_name> SET <logic> WHERE <that data u want to change>

 example 

 ```js
   UPDATES cats SET bread='shorthear' where bread='Tabby'; 
 ```

 # Delete 

   DELETE FROM <TABLE_NAME> WHERE <LOGIC>; 

   example

```js
  DELETE  FROM cats WHERE name='Egg'; 
```

