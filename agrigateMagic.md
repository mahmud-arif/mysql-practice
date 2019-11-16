#  Aggrigate 
   Built in function in sql that allow us to combine data
  
# count 

1.   How many books are in our database?
2.   How many author name??
3.   HOW many titles contains 'the'?

 ```js
  SELECT COUNT(*) FROM books; 
  SELECT COUNT(DISTINCT author_fname ) FROM books; 
  SELECT COUNT(*) FROM books WHERE title LIKE "%the%"; 
```

# Group By

  GROUP BY summarizes or aggregates identical data into single rows

1. Count how many books each author has written

```js
  SELECT author_lname count(*) FROM books GROUP BY author_lname; 

```

# MIN

1. find first release year of 1st book;
2. shortes number of pages in books; 

```js
SELECT MIN(released_year) FROM books;
SELECT MIN(pages) FROM books;
```

# max

```js
SELECT MIN(released_year) FROM books;
SELECT MIN(pages) FROM books;
```

# what if i want the title of the longest books?

```js
 SELECT title, pages FROM books WHERE pages=(SELECT MAX(pages) FROM books);
 SELECT title, pages FROM books WHERE pages=(SELECT MIN(pages) FROM books); 
                  or 
 SELECT title, pages  FROM books ORDER BY pages ASC LIMIT 1;  
 SELECT title, pages  FROM books ORDER BY pages DESC LIMIT 1; 
```

1. Q: find the year each author publish their first book. 

```js

  SELECT author_fname, author_lname, MIN(released_year) FROM books GROUP BY author_fname, author_lname; 

```

2. Q: find the longest page count for each author. 

```js
  SELECT author_fname, author_lname, max(pages) FROM books GROUP BY author_fname, author_lname; 

```

# sum 

 sums togather data

```js
 SELECT SUM(pages) FROM books;
 SELECT author_fname, author_lname, SUM(pages) FROM books GROUP BY author_fname, author_lname; 
```




  