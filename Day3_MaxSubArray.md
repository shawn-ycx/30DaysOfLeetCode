```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function(nums) {

  let currMax = globalMax = nums[0];
  for (let i = 1; i < nums.length; i++) {
     currMax = Math.max(nums[i], currMax + nums[i])
     
     if (currMax > globalMax) {
       globalMax = currMax
     }
  }
  return globalMax
};
```
