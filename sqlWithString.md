# how to run .sql file from sql cli; 

```js
  source <filePath.sql>
```

# concat data 
## combine data for cleaner output

  ```js
   concat(columnName,' ' ,  anotherColumn)

```

# substring(wroking with parts of string)

```
  SELECT SUBSTRING('hello world', 1, 4).. // hell  <SUBSTRING() || SUBSTR()>
  SELECT SUBSTRING('hello world', 7).. // world
  SELECT SUBSTRING('hello world', -3).. // rld
  
```

# replace

```js
 SELECT REPLACE('HELLO WORLD', 'HELL' 'ABC') // ABC WORLD

 ```
 # reverse string

 ```js
  SELECT REVERSE('HELLO WORLD')
  ```

  #char_length, UPPER AND LOWER

```js
   SELECT CHAR_LENGTH('HELLO WORLD)
   SELECT UPPER('hello world),
   SELECT LOWER('HELLO WORLD')
```
