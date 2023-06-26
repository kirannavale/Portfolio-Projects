# SQL Project Music Store Analysis
SQL project to analyze online music store data

## Objective:
The dataset consisted of information about employees, invoices, customers, tracks, genres, and countries. The goal is to extract valuable insights and provide answers to various ad-hoc questions related to the store's operations and customer behavior.

## Datasource :
Dataset used for this [Music_Data](https://github.com/kirannavale/Portfolio-Projects/tree/main/SQL%20Music%20Store%20Analysis/Data)

## Schema- Music Store Database  

![MusicDatabaseSchema](https://github.com/kirannavale/Portfolio-Projects/assets/34519689/48a1f0e3-2248-4164-921b-5241ae4afa19)

## Approach and Query Explanations:

1. Who is the senior most employee based on job title?
   - I wrote a query to retrieve the employee with the highest job title level and returned their name and job title.

2. Which countries have the most invoices?
   - I wrote a query to count the number of invoices for each country and sorted the results to identify the countries with the highest number of invoices.

3. What are the top 3 values of total invoice?
   - I wrote a query to retrieve the three highest total invoice values, ordering the results in descending order.

4. Which city has the best customers?
   - I wrote a query to calculate the sum of invoice totals for each city, sorted the results in descending order, and returned the city name and the sum of invoice totals.

5. Who is the best customer?
   - I wrote a query to determine the customer who has spent the most money by calculating the total amount spent by each customer and returning the person with the highest spending.

6. Write a query to return the email, first name, last name, and genre of all Rock Music listeners.
   - I wrote a query to retrieve the specified columns for customers who listen to Rock music, ordered the results alphabetically by email.

7. Let's invite the artists who have written the most rock music in our dataset.
   - I wrote a query to calculate the total track count for each artist who has written Rock music and returned the artist name and track count, sorting the results in descending order and limiting the output to the top 10.

8. Return all the track names that have a song length longer than the average song length.
   - I wrote a query to calculate the average song length, then retrieved the track names and milliseconds for tracks with a song length greater than the average, ordering the results by song length in descending order.

9. We want to find out the most popular music genre for each country.
   - I wrote a query to determine the genre with the highest number of purchases for each country. If multiple genres shared the maximum number of purchases, I included all of them in the results.

10. Write a query that determines the customer that has spent the most on music for each country.
    - I wrote a query to calculate the total amount spent by each customer for each country, identifying the top-spending customer for each country. If multiple customers shared the highest amount spent, I included all of them in the results.



