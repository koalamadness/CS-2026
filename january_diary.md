# Computer Science
## 2026/01/13

SELECT movies.title, domestic_sales, international_sales FROM boxoffice
INNER JOIN movies ON movies.id = boxoffice.movie_id;
SELECT movies.title, domestic_sales, international_sales FROM boxoffice
INNER JOIN movies ON movies.id = boxoffice.movie_id WHERE international_sales > domestic_sales;
SELECT movies.title, rating FROM boxoffice
INNER JOIN movies ON movies.id = boxoffice.movie_id 
ORDER BY rating DESC;
