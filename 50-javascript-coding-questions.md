
 
# 50 JavaScript Coding Interview Questions with Solutions

Beginner to Intermediate Level – Perfect for 0–2 Years Experience

---

# 1. Reverse a String

```js
function reverse(str) {
  return str.split("").reverse().join("");
}
````

---

# 2. Check Palindrome

```js
function isPalindrome(str) {
  return str === str.split("").reverse().join("");
}
```

---

# 3. Find Factorial

```js
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}
```

---

# 4. Fibonacci Series

```js
function fibonacci(n) {
  if (n <= 1) return n;
  return fibonacci(n-1) + fibonacci(n-2);
}
```

---

# 5. Find Largest Number in Array

```js
const largest = arr => Math.max(...arr);
```

---

# 6. Find Smallest Number

```js
const smallest = arr => Math.min(...arr);
```

---

# 7. Remove Duplicates

```js
const unique = arr => [...new Set(arr)];
```

---

# 8. Find Second Largest

```js
function secondLargest(arr) {
  return [...new Set(arr)].sort((a,b)=>b-a)[1];
}
```

---

# 9. Count Vowels

```js
function countVowels(str) {
  return str.match(/[aeiou]/gi)?.length || 0;
}
```

---

# 10. Check Prime Number

```js
function isPrime(n) {
  if (n < 2) return false;
  for (let i = 2; i <= Math.sqrt(n); i++) {
    if (n % i === 0) return false;
  }
  return true;
}
```

---

# 11. Sum of Array

```js
const sum = arr => arr.reduce((a,b)=>a+b,0);
```

---

# 12. Flatten Array

```js
const flatten = arr => arr.flat(Infinity);
```

---

# 13. Capitalize First Letter

```js
const capitalize = str => str.charAt(0).toUpperCase() + str.slice(1);
```

---

# 14. Reverse Number

```js
function reverseNumber(num) {
  return parseInt(num.toString().split("").reverse().join(""));
}
```

---

# 15. Check Anagram

```js
function isAnagram(a, b) {
  return a.split("").sort().join("") === b.split("").sort().join("");
}
```

---

# 16. Find Missing Number (1 to n)

```js
function missingNumber(arr, n) {
  return (n*(n+1))/2 - arr.reduce((a,b)=>a+b,0);
}
```

---

# 17. Swap Two Numbers

```js
let a=5, b=10;
[a,b] = [b,a];
```

---

# 18. Remove Falsy Values

```js
const removeFalsy = arr => arr.filter(Boolean);
```

---

# 19. Find Duplicates

```js
function findDuplicates(arr){
  return arr.filter((item,index)=>arr.indexOf(item)!==index);
}
```

---

# 20. Merge Two Arrays

```js
const merged = (a,b) => [...a,...b];
```

---

# 21. Intersection of Two Arrays

```js
const intersection = (a,b) => a.filter(x=>b.includes(x));
```

---

# 22. Check Even or Odd

```js
const isEven = n => n % 2 === 0;
```

---

# 23. Generate Random Number

```js
const random = (min,max)=>Math.floor(Math.random()*(max-min+1))+min;
```

---

# 24. Find GCD

```js
function gcd(a,b){
  return b===0?a:gcd(b,a%b);
}
```

---

# 25. Find LCM

```js
const lcm = (a,b)=>(a*b)/gcd(a,b);
```

---

# 26. Convert String to Title Case

```js
const titleCase = str =>
  str.split(" ").map(word=>word[0].toUpperCase()+word.slice(1)).join(" ");
```

---

# 27. Count Character Frequency

```js
function charCount(str){
  return [...str].reduce((acc,char)=>{
    acc[char]=(acc[char]||0)+1;
    return acc;
  },{});
}
```

---

# 28. Check Power of Two

```js
const isPowerOfTwo = n => (n & (n-1)) === 0 && n !== 0;
```

---

# 29. Debounce Function

```js
function debounce(fn,delay){
  let timeout;
  return function(){
    clearTimeout(timeout);
    timeout=setTimeout(()=>fn(),delay);
  };
}
```

---

# 30. Throttle Function

```js
function throttle(fn,limit){
  let wait=false;
  return function(){
    if(!wait){
      fn();
      wait=true;
      setTimeout(()=>wait=false,limit);
    }
  };
}
```

---

# 31. Deep Clone Object

```js
const deepClone = obj => JSON.parse(JSON.stringify(obj));
```

---

# 32. Check Empty Object

```js
const isEmpty = obj => Object.keys(obj).length === 0;
```

---

# 33. Convert Object to Array

```js
const objToArray = obj => Object.entries(obj);
```

---

# 34. Convert Array to Object

```js
const arrayToObj = arr => Object.fromEntries(arr);
```

---

# 35. Group By Property

```js
function groupBy(arr,key){
  return arr.reduce((acc,obj)=>{
    (acc[obj[key]]=acc[obj[key]]||[]).push(obj);
    return acc;
  },{});
}
```

---

# 36. Sort Array Ascending

```js
arr.sort((a,b)=>a-b);
```

---

# 37. Sort Array Descending

```js
arr.sort((a,b)=>b-a);
```

---

# 38. Find Longest Word

```js
const longestWord = str =>
  str.split(" ").reduce((a,b)=>a.length>b.length?a:b);
```

---

# 39. Check Substring

```js
const contains = (str,sub)=>str.includes(sub);
```

---

# 40. Convert Seconds to Time

```js
function secondsToTime(sec){
  let h=Math.floor(sec/3600);
  let m=Math.floor((sec%3600)/60);
  let s=sec%60;
  return `${h}:${m}:${s}`;
}
```

---

# 41. Find Average

```js
const average = arr => sum(arr)/arr.length;
```

---

# 42. Remove Element from Array

```js
const removeElement = (arr,val)=>arr.filter(item=>item!==val);
```

---

# 43. Chunk Array

```js
function chunk(arr,size){
  let res=[];
  for(let i=0;i<arr.length;i+=size){
    res.push(arr.slice(i,i+size));
  }
  return res;
}
```

---

# 44. Shuffle Array

```js
function shuffle(arr){
  return arr.sort(()=>Math.random()-0.5);
}
```

---

# 45. Check Armstrong Number

```js
function isArmstrong(num){
  let sum=num.toString().split("")
    .reduce((acc,d)=>acc+Math.pow(d,3),0);
  return sum==num;
}
```

---

# 46. Remove Spaces

```js
const removeSpaces=str=>str.replace(/\s/g,"");
```

---

# 47. Count Words

```js
const countWords=str=>str.trim().split(/\s+/).length;
```

---

# 48. Find First Non-Repeating Character

```js
function firstNonRepeat(str){
  for(let char of str){
    if(str.indexOf(char)===str.lastIndexOf(char)){
      return char;
    }
  }
}
```

---

# 49. Check Balanced Parentheses

```js
function isBalanced(str){
  let stack=[];
  for(let char of str){
    if(char==="(") stack.push(char);
    if(char===")") stack.pop();
  }
  return stack.length===0;
}
```

---

# 50. Memoization

```js
function memoize(fn){
  const cache={};
  return function(n){
    if(cache[n]) return cache[n];
    cache[n]=fn(n);
    return cache[n];
  };
}
```

---

# End of 50 Coding Questions

```

---

If you want next:

- 🔥 30 Tricky JavaScript Output Questions  
- 🚀 DSA Interview Questions for Backend Developers  
- 🧠 Node.js Coding Interview Questions  
- 💼 FAANG-Level JavaScript Questions  

Tell me what level you want next 👌
```
