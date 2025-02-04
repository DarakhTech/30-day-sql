```ruby
SELECT u.name, SUM(t.amount) as balance
FROM Users U
    LEFT JOIN Transactions t
    ON u.account = t.account
GROUP BY u.account
HAVING balance > 10000