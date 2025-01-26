```ruby
WITH CTE AS (
    SELECT
        num AS ConsecutiveNums,
        LEAD(num) OVER (ORDER BY id) AS next,
        LAG(num) OVER (ORDER BY id) AS prev
    FROM Logs
)
SELECT DISTINCT ConsecutiveNums
FROM CTE
WHERE ConsecutiveNums = prev
  AND prev = next;

- Common Table Expression CTE to create a view of table