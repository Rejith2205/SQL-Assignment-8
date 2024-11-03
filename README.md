## SQL-Assignment-8

### Consider the Country table and Persons table that you have created earlier and perform the following: 

### * 1 	Find the number of persons in each country.
      
 *select count(f_name) ,country_name disctinct  from person group by COUNTRY_NAME;*
 
### * 2.  Find the number of persons in each country sorted from high to low. 

*select count(f_name) ,country_name disctinct  from persons group by COUNTRY_NAME order by count(f_name) desc;*

### * 3.	Find out an average rating for Persons in respective countries if the average is greater than 3.0 

*Average rating of the person*

### Since THE average rate is greater than 3, find below the rating for each country.

*select avg(rating) ,country_name disctinct from persons group by COUNTRY_NAME;*

### * 4.	Find the countries with the same rating as the USA. (Use Subqueries) 

*SELECT count(rating),rating,country_name FROM persons where rating in (SELECT rating
FROM persons WHERE  country_name = 'usa') group by country_name,rating;*

### * 5. Select all countries whose population is greater than the average population of all nations. 

*select avg(population) from country;*

 *select population, country_name from country where population > (select avg(population) from country) 
  group by  population, country_name;*
  
### * 6. Create a database named Product 

*Create  DATABASE Product;*
### *7. create a table called Customer with the following fields in the Product database: Customer_Id - Make PRIMARY KEY First_name Last_name Email Phone_no Address City State Zip_code Country

*CREATE TABLE CUSTOMER (CUSTOMER_ID int NOT NULL,
    Last_Name varchar(255) NOT NULL,
    First_Name varchar(255) NOT NULL,
    EMAIL VARCHAR(200) NOT NULL,
    PHONE_NO INT(15) NOT NULL,
    ADDRESS VARCHAR(200) NOT NULL,
    CITY VARCHAR (50) NOT NULL,
    STATE VARCHAR 100) NOT NULL,
    ZIP_CODE VARCHAR(50) NOT NULL,
    COUNTRY VARCHAR(200) NOT NULL,
     PRIMARY KEY (CUSTOMER_ID));*
### *8.	Create a view named customer_info for the Customer table that displays Customer’s Full name and email address. 

*CREATE VIEW CUSTOMER_INFO    AS SELECT CONCAT(First_Name,  Last_Name)AS CUSTOMER_FULL_NAME,EMAIL FROM CUSTOMER;*
### *9.	Then perform the SELECT operation for the customer_info view. 

*SELECT * FROM CUSTOMER_INFO;*
### *10. Create a view named US_Customers that displays customers located in the US. 

*CREATE VIEW US_CUSTOMERS
   AS SELECT * FROM CUSTOMER
   WHERE COUNTRY='USA';*
*SELECT * FROM US_CUSTOMERS;*

### *11. Create another view named Customer_details with columns full name(Combine first_name and last_name), email, phone_no, and state.

*CREATE VIEW CUSTOMER_DETAILS
 AS SELECT CONCAT(First_Name,  Last_Name)AS CUSTOMER_FULL_NAME,EMAIL,PHONE_NO,STATE FROM CUSTOMER
   WHERE COUNTRY='USA';*
   
*SELECT * FROM CUSTOMER_DETAILS;*

   







