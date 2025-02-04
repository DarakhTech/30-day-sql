```ruby
SELECT Department, Employee, Salary
FROM (
    SELECT d.name as Department, e.name as Employee, e.salary as Salary, DENSE_RANK() OVER(PARTITION BY d.name ORDER BY e.salary DESC) as drank
    FROM Employee e
        LEFT JOIN Department d
        ON e.departmentId = d.id
) as T
WHERE drank <= 3

-- Dense rank with a partition was a new concept