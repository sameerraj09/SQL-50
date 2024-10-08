**1757**
```
SELECT product_id from Products 
WHERE low_fats='Y' && recyclable ='Y'
```
**584**
```
SELECT name from Customer where referee_id!=2 || referee_id is null
```
**595**
```
SELECT name , population ,area from World
where area >= 3000000 or population >=25000000;
```
**1148**
```
SELECT distinct author_id as id from Views where author_id = viewer_id order by author_id;
```
**1683**
```
select tweet_id from Tweets where length(content) > 15;
```
**1378**
```
Select u.unique_id ,e.name from Employees as e left join
EmployeeUNI as u on e.id = u.id;
```
**1068**
```
# Write your MySQL query statement below
Select p.product_name ,s.year,s.price from Sales as s left join product as p on s.product_id = p.product_id;
```
**HACKER RANK SQL QUERY IMPORTANT QUESTION:-**
![image](https://github.com/user-attachments/assets/8ce95526-911d-4546-a7e9-3e08f2f534f7)
Approach:- koi v operation ho bahar ek select laagane ka
```
SELECT
(SELECT COUNT(CITY) FROM STATION) -  (SELECT COUNT(DISTINCT CITY) FROM STATION);
```
Q:-Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
The STATION table is described as follows:
**Note:-** we can use two parameter in order by  caluse

```
(SELECT CITY, LENGTH(CITY) AS LEN
 FROM STATION
 ORDER BY LENGTH(CITY), CITY
 LIMIT 1)
 
UNION ALL

(SELECT CITY, LENGTH(CITY) AS LEN
 FROM STATION
 ORDER BY LENGTH(CITY) DESC, CITY
 LIMIT 1);
```
Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.
```
SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE "%a" or CITY LIKE "%e" or CITY LIKE "%i" or CITY LIKE "%o" or CITY LIKE "%u";
```
Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.
SUBSTRING(COL_NAME,STARTING POS,LENGTH)
```
SELECT DISTINCT CITY 
FROM 
STATION
WHERE 
SUBSTRING(CITY,1,1) IN ('a','e','i','o','u')
AND 
SUBSTRING(CITY,length(city),1) IN ('a','e','i','o','u');
```

![image](https://github.com/user-attachments/assets/8739bb60-a7eb-4bc8-9b00-9ffeb59c5a14)
```
SELECT NAME FROM STUDENTS WHERE MARKS>75 ORDER BY
SUBSTRING(NAME,LENGTH(NAME)-2,3) ,ID;
```
![image](https://github.com/user-attachments/assets/847a7ef4-172a-461f-aead-cbdd838e8e68)
```
SELECT NAME FROM EMPLOYEE ORDER BY NAME;
```
Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than 2000 per month who have been employees for less than 10 months. Sort your result by ascending employee_id.
```
SELECT NAME FROM EMPLOYEE WHERE SALARY> 2000 AND MONTHS <10 ORDER BY EMPLOYEE_ID
```
![image](https://github.com/user-attachments/assets/43e6d851-12fd-4e22-b6f3-0a357277742d)
Logic:-
SYNTAX OS SQL
CASE 
    WHEN 'CONDITION' THEN 'PRINT'
    ELSE 'PRINT'
    END AS 'VARIABLE NAME'
    
```
/*
Enter your query here.
*/
SELECT  
    CASE 
        WHEN A + B <= C OR B + C <= A OR C + A <= B THEN 'Not A Triangle'
        WHEN A = B AND B = C THEN 'Equilateral'
        WHEN A = B OR B = C OR C = A THEN 'Isosceles'
        ELSE 'Scalene'
    END AS TriangleType
FROM triangles;
```

![image](https://github.com/user-attachments/assets/4367989e-af6e-46ac-853e-89ae45de2c07)
**Learning:-**
Function:
Concat function take n no of input which we want to display togenther seprated by comma 
CONCAT(ATRIBUTES,'text',anythig);
substring(coulmn_name,position,size);
upper(coulmn name)
group by(to group rows based upon some property)
order by to arrange the row according to order

we can two query one after another to diplay two output

![image](https://github.com/user-attachments/assets/ea8c0222-b164-4aec-bf4c-e7c33654043e)
```
-- Query 1: Alphabetically ordered list of names with occupation initials
SELECT CONCAT(Name, '(', SUBSTRING(Occupation, 1, 1), ')') AS NameOccupation
FROM OCCUPATIONS
ORDER BY Name;

-- Query 2: Count of each occupation, sorted by count and then alphabetically
SELECT CONCAT('There are a total of ', COUNT(*), ' ', LOWER(Occupation), 's.')
FROM OCCUPATIONS
GROUP BY Occupation
ORDER BY COUNT(*), Occupation;
```

