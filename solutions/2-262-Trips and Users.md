```ruby
SELECT 
    t.request_at AS Day, 
    ROUND(SUM(status != 'completed') / COUNT(*), 2) AS 'Cancellation Rate' 
FROM Trips t
    LEFT JOIN Users c
        ON c.users_id = t.client_id
    LEFT JOIN Users d
        ON d.users_id = t.driver_id
WHERE 
    t.request_at BETWEEN '2013-10-01' AND '2013-10-03' 
    AND c.banned != 'Yes' 
    AND d.banned != 'Yes'
GROUP BY t.request_at;

- Not Hard just too many condition to follow so gets tedious