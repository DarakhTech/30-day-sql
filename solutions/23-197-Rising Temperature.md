```ruby
SELECT id as Id
FROM (
    SELECT id, temperature as temp_today, LAG(temperature) OVER(ORDER BY recordDate ASC) as temp_yesterday, recordDate as date_today, LAG(recordDate) OVER(ORDER BY recordDate ASC) as date_yesterday
    FROM Weather
) as T
WHERE temp_today > temp_yesterday AND DATEDIFF(date_today, date_yesterday) = 1

- LAG & DATEDIFF should be intuitive