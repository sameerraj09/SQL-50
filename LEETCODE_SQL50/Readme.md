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
