```ruby
SELECT score, RANK() OVER (ORDER BY score DESC) as 'rank'
FROM Scores

- RANK & DENSE_RANK should be used as window function 
- RANK is skips after repeating ones
- DENSE_RANK is continuous and create density of repeating ones
 