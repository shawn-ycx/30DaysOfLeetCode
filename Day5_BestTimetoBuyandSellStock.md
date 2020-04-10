```javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function (prices) {
  let bought = false
  let cost = null
  let day = 0
  let profit = 0

  while (day < prices.length) {
    if (!bought) {
      const price_today = prices[day]
      const price_tomorrow = prices[day + 1]
      if (price_tomorrow > price_today) {
        bought = true
        cost = price_today
      }
      day++
    } else {
      let future_day = day + 1
      while (true) {
        if (future_day === prices.length) {
          if (prices[future_day] > prices[day]) {
            profit += prices[future_day] - cost
            bought = false
            cost = null
            day = future_day
          } else {
            profit += prices[day] - cost
            bought = false
            cost = null
            day = day
          }
          break
        }

        if (prices[future_day] < prices[future_day-1]) {
          profit += prices[future_day-1] - cost
          bought = false
          cost = null
          day = future_day
          break
        }

        future_day++
      }
    }
  }

  return profit
}
```
