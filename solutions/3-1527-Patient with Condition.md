```ruby
SELECT *
FROM Patients
WHERE conditions LIKE 'DIAB1%' or conditions LIKE '% DIAB1%'

- Just the edge case of % DIAB1% required the thought process