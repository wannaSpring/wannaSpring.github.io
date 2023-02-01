---
title: leetcode
date: 2023-02-02 00:35:11
tags:
---

# Array
## Best Time to Buy and Sell Stock II

### Q
You are given an integer array prices where prices[i] is the price of a given stock on the ith day.

On each day, you may decide to buy and/or sell the stock. You can only hold at most one share of the stock at any time. However, you can buy it then immediately sell it on the same day.

Find and return the maximum profit you can achieve.

 

Example 1:

Input: prices = [7,1,5,3,6,4]
Output: 7
Explanation: Buy on day 2 (price = 1) and sell on day 3 (price = 5), profit = 5-1 = 4.
Then buy on day 4 (price = 3) and sell on day 5 (price = 6), profit = 6-3 = 3.
Total profit is 4 + 3 = 7.
Example 2:

Input: prices = [1,2,3,4,5]
Output: 4
Explanation: Buy on day 1 (price = 1) and sell on day 5 (price = 5), profit = 5-1 = 4.
Total profit is 4.
Example 3:

Input: prices = [7,6,4,3,1]
Output: 0
Explanation: There is no way to make a positive profit, so we never buy the stock to achieve the maximum profit of 0.
 

Constraints:

1 <= prices.length <= 3 * 104
0 <= prices[i] <= 104

### A
![Picsee-20230202010757.png](https://raw.githubusercontent.com/wannaSpring/snapshot/main/Picsee/Picsee-20230202010757iXdqzb.png?token=ALJ6LAXMA2IJBFUDXJGQ2MLD3KOKW)

```javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function(prices) {
    let i = 0
    let valley = prices[0]
    let peak = prices[0]
    let maxProfit = 0
    while (i < prices.length - 1) {
        // point continues to increase if current prices large than next prices. until we fount the lowest price.
        while((i < prices.length - 1) && (prices[i] >= prices[i + 1])){
            i++;
        }
        valley = prices[i]
        console.log(valley, 'valley')
        // point continues to increase if current prices small than next prices. until we fount the highest price.
        while((i < prices.length - 1) && (prices[i] <= prices[i + 1])){
            i++;
        }
        peak = prices[i]
        console.log(peak,'peak')
        // add all of the difference between peak and valley
        maxProfit += peak - valley
        
    }
    return maxProfit;
};
```
![Picsee-20230202010436.png](https://raw.githubusercontent.com/wannaSpring/snapshot/main/Picsee/Picsee-20230202010436Y2vVU2.png?token=ALJ6LASYJLVF7O4BPFG2KRLD3KN6E)







