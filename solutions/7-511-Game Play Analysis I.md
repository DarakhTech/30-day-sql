```ruby
SELECT player_id, MIN(event_date) as first_login
FROM Activity
GROUP BY player_id

- Straight forward
- Can use TO_CHAR(MIN(event_date),'YYYY-MM-DD') 