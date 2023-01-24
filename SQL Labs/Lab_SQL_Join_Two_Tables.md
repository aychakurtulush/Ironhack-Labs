# Lab | SQL Queries - Join Two Tables
use sakila;

# 1. Which actor has appeared in the most films? 

SELECT actor_id, COUNT(film_id) as films_appeared
FROM film_actor
GROUP BY actor_id
ORDER BY films_appeared DESC;

# 2. Most active customer (the customer that has rented the most number of films)

SELECT customer_id, COUNT(rental_id) as films_rented
FROM rental
GROUP BY customer_id
ORDER BY films_rented DESC
LIMIT 1;

# 3. List number of films per `category`.

SELECT c.name, COUNT(f.film_id) as films_count
FROM category c
JOIN film_category fc 
ON c.category_id = fc.category_id
JOIN film f 
ON fc.film_id = f.film_id
GROUP BY c.category_id
ORDER BY films_count DESC;

# 4. Display the first and last names, as well as the address, of each staff member.

SELECT s.first_name, s.last_name, a.address
FROM staff s
JOIN address a ON s.address_id = a.address_id;

# 5. get films titles where the film language is either English or italian, 
and whose titles starts with letter "M" , sorted by title descending.

SELECT title
FROM film
WHERE language_id IN (1, 7) AND title LIKE 'M%'
ORDER BY title DESC;

# 6. Display the total amount rung up by each staff member in August of 2005.

SELECT staff_id, SUM(amount) as total_amount
FROM payment
WHERE staff_id IS NOT NULL
AND MONTH(payment_date) = 8
AND YEAR(payment_date) = 2005
GROUP BY staff_id;

# 7. List each film and the number of actors who are listed for that film.



# 8. Using the tables `payment` and `customer` and the JOIN command, list the total paid by each customer. List the customers alphabetically by last name.


# 9. Write sql statement to check if you can find any actor who never particiapted in any film. 



# 10. get the addresses that has NO customers, and ends with the letter "e" 



# **Optional**: what is the most rented film?


