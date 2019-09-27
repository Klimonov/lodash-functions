# Lodash functions

## _.chunk(array, [size=1])
Creates an array of elements split into groups the length of size. If array can't be split evenly, the final chunk will be the remaining elements.

```javascript
_.chunk(['a', 'b', 'c', 'd'], 2);

// => [['a', 'b'], ['c', 'd']]

_.chunk(['a', 'b', 'c', 'd'], 3);

// => [['a', 'b', 'c'], ['d']]
```
```javascript
const chunk = (arr, count) => {
  const start = [arr.slice(0, count)];
  const end = arr.slice(count);
  start.push(end);
  return start;
}
```  

## _.compact(array)

Creates an array with all falsey values removed. The values false, null, 0, "", undefined, and NaN are falsey.

```javascript
_.compact([0, 1, false, 2, '', 3, NaN, 5]);
// => [1, 2, 3]
```
```javascript
const compact = arr => {
   let result = [];
   for (let i = 0; i < arr.length; i += 1) {
     if (arr[i]) {
       result.push(arr[i]);
     }
   }
   return result;
};

//-----------

const compact = arr => arr.filter(x => x);
```  

## _.concat(array, [values])

Creates a new array concatenating array with any additional arrays and/or values.

```javascript
var array = [1];
var other = _.concat(array, 2, [3, 6], [[4]]);
 
console.log(other);
// => [1, 2, 3, [4]]
 
console.log(array);
// => [1]
```
```javascript
const concat = (...arguments) => {
  let result = [];
  for (let argument of arguments) result.push(argument);
  return result;
}
```  


