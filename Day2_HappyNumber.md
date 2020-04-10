```javascript
/**
 * @param {number} n
 * @return {boolean}
 */
var isHappy = function(n) {
    let seen = {}
    const toSquare = (number) => number ** 2;
    const toDigits = (number) => Array.from([...number + ''].map(Number), toSquare);
    const toSum = (acc, strDigit) => acc + strDigit;
    
    while(n !== 1) {
        n = n < 10 ? toSquare(n) : toDigits(n).reduce(toSum);
        
        // return false to prevent infinite loop
        if (seen[n]) {
            return false;
        }
        
        seen[n] = true;
    }
    
    return true
};
```
