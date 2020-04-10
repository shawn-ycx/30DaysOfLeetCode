```js
/**
 * @param {number[]} arr
 * @return {number}
 */
var countElements = function(arr) {
    let count = 0;
    arr.forEach(num => arr.includes(num+1) && count++)
    return count
};
```
