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
3. ### Find the Even numbers from an array 

```javascript
const array = [12,4,5,77,8,8]
const allEvens = [];

for (let i = 0; i < array.length; i++) {
  if(array[i]%2 === 0){
    allEvens.push(array[i])
  }
}
console.log("allEvens:", allEvens)
```
4. ### Find the element whose addition of digits in max in an array 

```javascript
const array = [12,4,5,77,8,8]

const additionOfDigits = [];
let max = 0
let maxElement = 0;

for (let i = 0; i < array.length; i++) {
  let element = array[i];
  let result = 0;
  while( element!== 0){
    result = result + Math.trunc(element%10);
    element = element/10;
  }
  if(result%2==0){
   if(max<result){
     max = result
     maxElement = array[i];
   } 
  additionOfDigits.push(result)
  }
}
console.log("allEvens:", additionOfDigits)
console.log("maxElement", maxElement)
```

5. ### Find the Palindrome elements from an array 

```javascript
const array = [12321,45489,545,7556647,845,8668]

const palindrome = array.filter(elm=>{
let num = elm;
let reversedNum = 0;
while(num !=0){
  reversedNum = 10*reversedNum + Math.trunc(num%10)
  num = Math.trunc(num/10);
}
  if(elm===reversedNum){
    return elm
  }
})
console.log("palindrome", palindrome)
```
6. ### Print first N numbers 

```javascript

for (let i = 2; i <= 20; i++) {
  let isPrime = true;
  for (let j = 2; j <i; j++) {
    if(i%j==0){
      isPrime=false;
      break;
    }    
  }
  if(isPrime){
    console.log(i)
  }
}
```
