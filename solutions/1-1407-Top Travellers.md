```ruby
SELECT u.name, COALESCE(SUM(r.distance),0) as travelled_distance
FROM Users u
    LEFT JOIN Rides r
    ON r.user_id = u.id
GROUP BY r.user_id
ORDER BY travelled_distance DESC, u.name ASC 

--

- COALESCE for the NULL value
- GROUP_BY to handle multiple rides

--
Fairly straightforward 