1. ### Find the Maximum value in an array

```javascript
const array = [12,4,5,77,8,8]
let max = array[0]; 

for (let i = 0; i < array.length; i++) {
  if(max < array[i]){
    max = array[i]
  }
}
console.log("max:", max)
```
2. ### Addition of the digits 

```javascript
let num = 1923;
var result = 0;

while(num!=0){
  result = result + Math.trunc(num%10) 
  num = Math.trunc(num/10);
}
console.log("Addition: ", result)
```
