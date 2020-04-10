```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var moveZeroes = function(nums) {
    let newLen = nums.length;

  for (let i = 0; i < newLen; i++) {
    if (nums[i] === 0) {
      nums.splice(i, 1);
      nums.push(0);
      i -= 1;
      newLen -= 1;
    }
  }
};
```
