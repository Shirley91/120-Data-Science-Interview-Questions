## Programming (14 questions)
Solutions are in code.ipynb

#### 1. Write a function to calculate all possible assignment vectors of 2n users, where n users are assigned to group 0 (control), and n users are assigned to group 1 (treatment).
  - Build-in function
  - Recursive programming
  
#### 2. Given a list of tweets, determine the top 10 most used hashtags.
  - Store all the hashtags in a dictionary and get the top 10 values using sql query
  - Priority Queue for large dataset and realtime topK problem
  
#### 3. Program an algorithm to find the best approximate solution to the knapsack problem in a given time.
  - Knapsack problem (https://en.wikipedia.org/wiki/Knapsack_problem)
  - Greedy solution (add the best v/w as much as possible and move on to the next)
    - add items in decreasing order of v/w
    - add items in decreasing order of v
    
#### 4. Program an algorithm to find the best approximate solution to the travelling salesman problem in a given time.
  - Travelling salesman problem (https://en.wikipedia.org/wiki/Travelling_salesman_problem)
  - Lin-Kernighan algorithm (http://arthur.maheo.net/implementing-lin-kernighan-in-python/)
  - 2-opt algorithm (https://en.wikipedia.org/wiki/2-opt)
  
#### 5. You have a stream of data coming in of size n, but you don’t know what n is ahead of time. Write an algorithm that will take a random sample of k elements. Can you write one that takes O(k) space?
  - Reservoir sampling (https://en.wikipedia.org/wiki/Reservoir_sampling)
  - more info (http://web.archive.org/web/20141026071430/http://propersubset.com:80/2010/04/choosing-random-elements.html)

#### 6. Write an algorithm that can calculate the square root of a number.
  - (https://www.quora.com/What-is-the-method-to-calculate-a-square-root-by-hand?redirected_qid=664405)
  - (https://www.quora.com/How-do-I-write-a-program-for-finding-the-square-root-of-a-number-without-using-the-sqrt-function)
  
#### 7. Given a list of numbers, can you return the outliers?
  - sort all numbers, then get Q1 and Q3 to calculate IQR = Q3 - Q1, then find outliers if the number larger than Q3 + 1.5IQR or smaller than Q1 - 1.5IQR.
  
#### 8. When can parallelism make your algorithms run faster? When could it make your algorithms run slower?
  - Parallelism is a good idea when the task can be divided into sub-tasks that can be executed independent of each other without communication or shared resources. Even then, efficient implementation is key to achieving the benefits of parallelization. In real-life, most of the programs have some sections that need to be executed in serialized fashion, and the parallelizable sub-tasks need some kind of synchronization or data transfer. Thus, it is hard to predict whether parallelization will actually make the algorithm run faster than the serialized approach.
  - compute in parallel when communication cost < computation cost
    - ensemble trees
    - minibatch
    - cross validation
    - forward propagation
    - minibatch
    - not suitable for online learning
  - more info (https://www.quora.com/When-can-parallelism-make-your-algorithms-run-faster-When-could-it-make-your-algorithms-run-slower-1)

#### 9. What are the different types of joins? What are the diffences between them?
  - Inner Join: elements in both dataframes
  - Left Join: elements in left dataframes and elements in both dataframes
  - Right Join: elements in right dataframes and elements in both dataframes
  - Self Join: join the dataframe itself
  - Full Outer Join: all elements of two dataframes (elements in either left dataframe or right dataframe)

#### 10. Why might a join on a subquery be slow? How might you speed it up?
  - Subqueries, especially with correlated subqueries where the is dependent on the outer query, the correlated subquery requires more or one values to be passed to it by the outer query before the subquery can be resolved. This means that you need to process the subquery more times, one for each row in the outer query. In particular, in this case, if the inner and outer query returns M and N rows, respectively, the total run time could be O(M * N).
  - Change the subquery to a join.
  - more info (https://www.quora.com/Why-might-a-join-on-a-subquery-be-slow-How-might-you-speed-it-up)
  
#### 11. Describe the difference between primary keys and foreign keys in a SQL database.
  - Primary keys are columns whose value combinations must be unique in a specific table so that each row can be referenced uniquely. 
    - constraint uniquely identifies each record in a database table 
    - must contain unique values, cannot contain NULL values
    - a table can have only one primary key, which may consist of single or multiple fields
  - Foreign keys are columns that references columns (often primary keys) in other tables.
    - a key used to link two tables together
    - a field or collection of field in one table that refers to the primary key in another table
  
#### 12. Given a COURSES table with columns course_id and course_name, a FACULTY table with columns faculty_id and faculty_name, and a COURSE_FACULTY table with columns faculty_id and course_id, how would you return a list of faculty who teach a course given the name of a course?
  - select faculty_name from faculty_id c join (select faculty_id from (select course_id from COURSES where course_name=xxx) as a join COURSE_FACULTY b on a.course_id = b.course_id) d on c.faculty_id = d.faculty_id
  - select f.faculty_name from faculty f join course_faculty cf on c.faculty_id = cf.faculty_id where cf.course_id = (select course_id from course where course_name = 'xxx');
  
#### 13. Given a IMPRESSIONS table with ad_id, click (an indicator that the ad was clicked), and date, write a SQL query that will tell me the click-through-rate of each ad by month.
  - select ad_id, distinct month(date) as month, average(click) as CTR from IMPRESSIONS group by ad_id, month(date);
  
#### 14. Write a query that returns the name of each department and a count of the number of employees in each:  
#### EMPLOYEES containing: Emp_ID (Primary key) and Emp_Name  
#### EMPLOYEE_DEPT containing: Emp_ID (Foreign key) and Dept_ID (Foreign key)  
#### DEPTS containing: Dept_ID (Primary key) and Dept_Name

  - select d.Dept_Name, count( e.* ) as number from EMPLOYEES e left join EMPLOYEE_DEPT ed on e.Emp_ID = ed.Emp_ID left join DEPTS d on d.Dept_ID = ed.Dept_ID group by d.Dept_ID, d.Dept_Name;
