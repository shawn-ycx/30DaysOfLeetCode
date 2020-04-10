```js
/**
 * @param {string[]} strs
 * @return {string[][]}
 */
var groupAnagrams = function(strs) {
    let groups = {}
    
    strs.forEach(str => {
        const sorted = str.split('').sort()
        groups[sorted] ? groups[sorted].push(str) : groups[sorted] = [str];
    })
    
    return Object.values(groups)
};
```
