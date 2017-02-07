# simple-sql-queries

For today we will be practicing inserting and querying data using SQL.

Here is a website that will let us write queries to interact with some data.  [http://jxs.me/chinook-web/](http://jxs.me/chinook-web/)  

On the left are the Tables with their fields.  The right is where we will be writing our queries.  The bottom is where we will see our results.  

Any new tables or records that we add into the database will be removed after you refresh the page.  So if you're wondering where you data went, that may be why.

Use [www.sqlteaching.com](http://www.sqlteaching.com/) or [sqlbolt.com](http://sqlbolt.com/) as resources for the missing keywords you'll need.

## PERSON
1. Create a table called Person that records a person's Name, Age, Height, City, FavoriteColor, and Id.  Id should be an auto-incrementing id/primary key.
<!-- /* Create Table tb
(
  	Id INTEGER PRIMARY KEY,
  	Name VARCHAR(40),
  	Age INTEGER,
  	Height INTEGER,
  	City text,
  	FavoriteColor text
  ); */  -->
2. Add 5 different people into the Person database.  Remember to not include the Id because it should auto-increment.
<!--
Insert into tb (name, age, height, City, favoriteColor) Values
("Juan", 24, 168, 'Provo', 'Red'),
("Pablo", 30, 120, 'Salt Lake City', 'Red'),
("Carlos", 16, 188, 'Las Vegas', 'Dark Blue'),
("John", 26, 186, 'Mormon Town', "Sky Blue"),
("Pedro", 20, 177, "Illegal", "Green") -->
3. List the people in the Person table by Height from tallest to shortest (descending)
<!-- select * from tb order by Height DESC  -->
(For this database to create an auto incrementing field set it's type to INTEGER PRIMARY KEY AUTOINCREMENT)

  * List the people in the Person table by Height from shortest to tallest (ascending)
  <!-- select * from tb order by Height asc -->
  * List all the people in the Person table by oldest first
  <!-- select * from tb order by age desc -->
  * List all the people in the Person table older than age 20.
  <!-- select * from tb where Age > 20 -->
  * List all the people in the Person table that are exactly 18.
  <!-- select * from tb where Age = 18 -->
  * List all Person that are less than 20 and older than 30.
  <!-- select name, age from tb where Age < 20 or Age > 30 -->
  * List all Person that are not 27 (Use not equals)
  <!-- select name, age from tb where age != 27 -->
  * List all Person where their favorite color is not red
  <!-- select name, favoriteColor from tb where favoriteColor != 'Red' -->
  * List all Person where their favorite color is not red or blue
   <!-- select name, favoriteColor from tb where favoriteColor != 'Red' and  favoriteColor != 'Dark Blue' -->
  * List all Person where their favorite color is orange or green
  <!-- select name, favoriteColor from tb where favoriteColor = 'orange' or favoritecolor = 'Green' -->
  * List all Person where their favorite color is orange, green or blue (use IN)
  <!-- select name, favoriteColor from tb where favoriteColor in ('orange', 'green', 'blue') -->
  * List all Person where their favorite color is yellow or purple
  <!-- select name from tb where favoriteColor in ('yellow', 'purple') -->

## ORDER
4. Create a table called Orders that records the productName, productPrice, Quantity, and personId
<!-- create Table Orders
(
productName text,
productPrice integer,
Quantity integer,  
personId integer primary key
);  -->

5. Add 5 Orders to Order table
<!-- /*  insert into Orders(productName, productPrice, Quantity) values
 ('the good stuff', 10000, 1),
 ('pasties', 3, 100),
 ('gloves', 10, 1),
 ('taco bell', 12, 4),
 ('doritos', 3, 3) */ -->
6. Select all the records from the Order table

  * Calculate the total number of products Ordered
  <!-- select sum(Quantity) from Orders -->
  * Calculate the total Order Price
  <!-- select sum(productPrice) from Orders -->
  * Calculate the total Order Price By personId (If you only made orders for 1 person, go add more for the other people)
  <!-- select personId, sum(productPrice) from Orders
group by personId */ -->

## Artists
7. Add 3 new Artists to the Artist table
<!-- /* insert into Artist(Name) values
("The Weeknd")
 */
/* select name, ArtistId from Artist where name = 'The Weeknd' */
/* insert into Artist(Name) values ("Selena Gomez") */
/* insert into Artist(Name) values ("Justin Bieber") */ -->

 * Select the top 10 artists in reverse alphabetical order
 <!-- select * from Artist order by name desc limit 10 -->
 * Select the top 5 artists in alphabetical order
 <!-- select * from Artist order by name asc limit 5 -->
 * Select all artists that start with the word Black
 <!-- select * from Artist where Name like 'black%' % at the end checks for string at  the begining  -->
 * Select all artists that contain the word Black
 <!-- select * from Artist where Name like '%black%' front and back checks if contains-->

## Employee
8. Add 2 new Employees to the Employee table
<!-- insert into Employee(LastName, FirstName) values("Carlos", "Juan") -->
* List all Employee first and last names only that live in Calgary
<!-- select FirstName, LastName, City from Employee where city = 'Calgary' -->
* Find the first and last name for the youngest employee
<!-- select  FirstName, LastName, max(BirthDate) from Employee -->
* Find the first and last name for the oldest employee
<!-- select  FirstName, LastName, min(BirthDate) from Employee -->
* Find everyone that reports to Nancy Edwards (Use the ReportsTo column)
<!-- select FirstName from Employee where ReportsTo = 2 -->
* Count how many people live in Lethbridge
<!-- select count(*) from Employee where city = 'Lethbridge' -->


## Invoice
9. Use the Invoice table for the following

* Count how many orders were made from the USA
<!-- select count(*) from Invoice where BillingCountry = "USA" -->
* Find the largest order total amount
<!-- select max(Total) from Invoice -->
* Find the smallest order total amount
<!-- select min(Total) from Invoice -->
* Find all orders bigger than $5
<!-- select * from Invoice where Total > 5; -->
* Count how many orders were smaller than $5
<!-- select * from Invoice where Total < 5; -->
* Count how many orders were in CA, TX, or AZ (use IN)
<!-- select count(*) from Invoice where BillingState in ('CA', 'TX', 'AZ')  all 3 states-->
* Get the average total of the orders
<!-- select avg(Total) from Invoice -->
* Get the total sum of the orders
  <!-- select sum(Total) fron Invoice -->

## Copyright

© DevMountain LLC, 2016. Unauthorized use and/or duplication of this material without express and written permission from DevMountain, LLC is strictly prohibited. Excerpts and links may be used, provided that full and clear credit is given to DevMountain with appropriate and specific direction to the original content.
