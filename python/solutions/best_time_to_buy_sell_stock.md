## Best time to buy and sell stock

```python
def max_profit(prices):
    if len(prices) == 0:
        return 0
    
    max_profit = 0
    min_price = prices[0]

    for price in prices:
        if price < min_price:
            min_price = price
        else:
            max_profit = max(max_profit, price - min_price)
    return max_profit

prices = [7,1,5,3,6,4]
print(max_profit(prices))

prices = [7,6,4,3,1]
print(max_profit(prices))

prices = []
print(max_profit(prices))
```
