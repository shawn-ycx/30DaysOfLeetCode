```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var singleNumber = function(nums) {
    // Sample: [2,2,1]
    // 2 ^ 2 ^ 1 
    // 0010 ^ 0010 ^ 0001
    // 0000 ^ 0001
    // => 0001 => 1
    
    // Sample: [4,1,2,1,2]
    // 4 ^ 1 ^ 2 ^ 1 ^ 2
    // (0100 ^ 0001) ^ 0010 ^ 0001 ^ 0010
    // (0101 ^ 0010) ^ 0001 ^ 0010
    // (0111 ^ 0001) ^ 0010
    // (0110 ^ 0010)
    // => 0100 => 4
    
    // XOR Operator
    return nums.reduce((prev,next) => prev ^ next)
};
```
