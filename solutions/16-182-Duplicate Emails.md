```ruby
SELECT DISTINCT email
FROM Person
#WHERE email IS NOT NULL 
GROUP BY email
HAVING COUNT(*) > 1

- NULL cannot meet the COUNT(*) > 1 condition, the email IS NOT NULL condition is redundant and can be removed