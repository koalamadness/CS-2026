# Computer Science
## 2026/01/13

SELECT movies.title, domestic_sales, international_sales FROM boxoffice
INNER JOIN movies ON movies.id = boxoffice.movie_id;
SELECT movies.title, domestic_sales, international_sales FROM boxoffice
INNER JOIN movies ON movies.id = boxoffice.movie_id WHERE international_sales > domestic_sales;
SELECT movies.title, rating FROM boxoffice
INNER JOIN movies ON movies.id = boxoffice.movie_id 
ORDER BY rating DESC;

SELECT DISTINCT building_name FROM buildings LEFT JOIN employees ON building_name = building WHERE role NOT NULL;
SELECT DISTINCT building_name ,capacity FROM buildings LEFT JOIN employees ON building_name = building;
SELECT DISTINCT building_name, role FROM buildings LEFT JOIN employees ON building_name = building;

SELECT name, role FROM employees WHERE building IS NULL;
SELECT building_name FROM buildings LEFT JOIN employees ON building = building_name WHERE role IS NULL;

SELECT title, (domestic_sales + international_sales) / 1000000 AS total_sales_inM FROM movies LEFT JOIN boxoffice ON id = movie_id ;
SELECT title, rating/10 * 100 FROM movies LEFT JOIN boxoffice ON id = movie_id ;
SELECT title, rating * 10 AS rating_percent
FROM movies
  JOIN boxoffice
    ON movies.id = boxoffice.movie_id;
SELECT title, year
FROM movies
WHERE year % 2 = 0;
