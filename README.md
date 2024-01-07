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

. ### Find the Factorial 

```javascript
1. Using the While Loop

var num = 5;
var ans = 1;
while(num!==0){
	ans = ans* num
	num--;
}
console.log("Factorial is: ", ans)

2. Using the Recursion

function FindTheFactorial(num){
	if(num==0){
		return 1;
	}else{
		return num * FindTheFactorial(num-1)
	}
}

3. Using For Loop 

var ans = 1;
var num = 5;

for(let i=1; i<=num; i++){
	ans = ans* i
}
console.log("The factorial is", num)
```



7. ### Find the Fibonacci Series of N numbers 

```javascript

var num1 = 0;
var num2 = 1;
var target = 10;

for (let i = 0; i < target; i++){
   console.log(num1);
   var nextTerm = num1 + num2;;
   num1 = num2;
   num2= nextTerm;
}

```

8. ### Bubble Sort  

```javascript

//Bubble sort

var array = [10, 3, -5, -22, 54, 0, 0, -22, 34, -66, -2, 6,7, 77, 33]

// Compare the first element with all others 
// If the first element is max than second then just swap it. 
// Require two loops so that one element can iterate on all others 
// Every iteration of the outer loop will sort the first element
// So, dont need to iterate for the last one as it will get sorted before it
// Second loop needs to start iteration from the next index of the first loop. 

function bubbleSort(array){
   if(array.length===0){
      return -1
   }
   for (let i = 0; i < array.length-1; i++) {
      for (let j = i+1; j < array.length; j++) {
         if(array[i]> array[j]){
            swap(array,i, j)
         }
      }      
   }
   console.log("Bubble Sorted array", array)
}

function swap(array, maxIndex, end){
   var temp = array[maxIndex];
   array[maxIndex] = array[end];
   array[end] = temp;
}
bubbleSort(array)

```

9. ### Selection Sort  

```javascript

//selection sort

var array = [10, 3, 5, 22, 54, 66, 2, 6,7, 77, 33]

function selectionSort(array){

   // first find the index of the Max element
   // Replace that element with the last element
   // start index will be constant
   // end index will keep on changing

   var start = 0;
   for (let i = 0; i < array.length; i++) {
      var end = array.length-1-i;
      var maxIndex = findMaxElement(array, start, end);
      swap(array, maxIndex, end);
   }
   console.log("Sorted array", array)
}

function swap(array, maxIndex, end){
   var temp = array[maxIndex];
   array[maxIndex] = array[end];
   array[end] = temp;
}

function findMaxElement(array, start, end){
   var max = 0
   for (let i = 0; i < end; i++) {
         if(array[max]<array[i]){
            max = i;
         }      
   }
   return max;
}
selectionSort(array)

```

10. ### Remove duplicates from an array
```javascript

//Remove Duplicates

var array = [10, 20, 20, 30, 10, 30, 40, 58, 31, 32, 31]

var unique = [];

for (let i = 0; i < array.length; i++) {
   let isDup = false;
   for (let j = i+1; j < array.length; j++) {
      if(array[i]==array[j]){
         isDup=true
         break;
      }
   }
   if(!isDup){
      unique.push(array[i])         
   }
}

console.log(unique)

// Second Method

function removeDuplicates(array){
   let unique = []
   array.forEach(el=>{
      if(!unique.includes(el)){
         unique.push(el)
      }
   })
   console.log("Unique Arrays", unique)
}

removeDuplicates([0, 0, 1, 1, 1, 2, 2, 3, 3, 4]);

//Third Method- Using the ES6 features


function removeDuplicates3(array){
   let unique = [...new Set(array)]
   console.log("Unique Arrays", unique)
		return unique
}

//Fourth Method - using the first IndexOf() method

function removeDuplicates4(array){
   let unique = array.filter((el, index)=>array.indexOf(el)==index)
 console.log("Unique Arrays", unique)
}

//Fifth Method

function removeDuplicates3(array){
   let unique = array.reduce((acc, current)=>{
      if(acc.indexOf(current) === -1){
         acc.push(current)
      }
      return acc
   },[])
   console.log("Unique Arrays", unique)
}

removeDuplicates3([0, 0, 1, 1, 1, 2, 2, 3, 3, 4]);

```
11. ### Reverse a String
```javascript

function reverseString(str){
 var reversed = []
 for (let i = str.length-1; i >=0; i--) {
   reversed.push(str[i])
 }
   console.log("reversed", reversed) 
 return reversed.join("")
}

reverseWord("SkeeG")

/**
 * Using Two Pointers Method
 * @param {character[]} s
 * @return {void} Do not return anything, modify s in-place instead.
 */
var reverseString = function (s) {
    let start = 0;
    let end = s.length-1;
    while(start<=end) {
        let temp = s[start]
        s[start] = s[end]
        s[end] = temp;
        start++;
        end--;
    }
};
```
