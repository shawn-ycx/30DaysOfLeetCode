```js
/**
 * @param {string} S
 * @param {string} T
 * @return {boolean}
 */
var backspaceCompare = function(S, T) {
    const findTrueString = (str) => {
      let runner = 0;
      str = str.split('')
      while (runner < str.length){
        if (runner < 0) runner = 0

        if (str[runner] === '#') {
          str[runner] && str.splice(runner, 1)
          str[runner-1] && str.splice(runner-1, 1)
          runner--;
        } else {
          runner++;
        }
      }

      return str.length ? str.join('') : '';
    }
    return findTrueString(S) === findTrueString(T);
};
```
