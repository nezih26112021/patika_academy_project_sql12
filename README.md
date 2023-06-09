# patika_academy_project_sql12
query scenarios

Perform the following query scenarios on the "dvdrental" sample database:

1. In the movie table, the movie length is shown in the length column. How many movies are longer than the average movie length?

SELECT COUNT(*) FROM film

WHERE length>

(SELECT AVG(length) FROM film);

2. How many movies have the highest "rental_rate" in the movie table?

SELECT COUNT(*) FROM film

WHERE rental_rate=

(SELECT MAX(rental_rate) FROM film);

3. In the movie table, list the movies with the lowest "rental rate" and the lowest "replacement cost" values:

SELECT * FROM film

WHERE rental_rate=

(SELECT MIN(rental_rate) FROM film)

AND replacement_cost=

(SELECT MIN(replacement_cost) FROM film);

4. In the payment table, list the customers who make the most purchases:

SELECT customer_id, COUNT(customer_id) AS most_buy FROM payment

GROUP BY customer_id

ORDER BY most_buy DESC;
