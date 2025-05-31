# DSA

### 1.  Given an integer x, return true if x is palindrome integer.

    An integer is a palindrome when it reads the same backward as forward.

    For example, 121 is a palindrome while 123 is not.
    
    const palindrome = (nums) =>{

        const orderedNum = nums.toString().split("").reverse().join("");

        if(nums === ~~orderedNum){

            return true

        }else{

            return false

         }



    }

    OR

    const isPalindrom = (n) => {
	  return Number((n+"").split('').reverse().join('')) === n
	}
    
### 2. Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

    You must implement a solution with a linear runtime complexity and use only constant extra space.
    
   const sol = (arr) => {
      const obj = {}
      for (let i = 0; i < arr.length; i++){
        obj[arr[i]] = obj[arr[i]]+1 || 1
      }

      for(x in obj){

        if(obj[x] === 1){
         return x
        }
      }
    } 
    
    
### 3. Implement strStr().

    Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

    Clarification:

    What should we return when needle is an empty string? This is a great question to ask during an interview.

    For the purpose of this problem, we will return 0 when needle is an empty string. This is consistent to C's strstr() and Java's indexOf().
    
    
    function strStr(haystack: string, needle: string): number {
        const index = haystack.indexOf(needle)

        return index

    };
    
    
### 4. Given a string s consisting of some words separated by some number of spaces, return the length of the last word in the string.

    A word is a maximal substring consisting of non-space characters only.

    const lengthOflastWord = (n) => {
	  return n.split(' ')[n.split(' ').length - 1].length
     }

### 5. Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

    const longestContinousSubArray = (arr) => {
	  let solution = arr[0]
	  for (let i = 1; i < arr.length; i++){
	    arr[i] = Math.max(arr[i], arr[i - 1] + arr[i])
	    solution = Math.max(solution,arr[i])
	  }
	
	  return solution
   }
    
### 6. A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and            backward. Alphanumeric characters include letters and numbers.
    
        Given a string s, return true if it is a palindrome, or false otherwise.
       
       function isPalindrome(s: string): boolean {
       
              const splitString = s.split("")
              
              const checkAlphaNum = splitString.filter((i)=> i.match(/^[0-9a-zA-Z]+$/))

              const changeCase = checkAlphaNum.join("").toLowerCase()

              const reverse = changeCase.split("").reverse().join("")

              if( reverse === changeCase ){
                return true
              }else{
                return false
              }
        };
        
### 7. Reverse integer
    
    const revNum = (num) => {
      const res = parseInt(num.toString().split('').reverse().join(''))

      if(num < 0){
        return res * -1
      }
      return res
    }
    
## 8. Write a program that console logs the numbers from 1 to n. But for multiples of three print “fizz” instead of the number and for the multiples of five print “buzz”. For numbers which are multiples of both three and five print “fizzbuzz”.
 --- Example
   fizzBuzz(5);
   1
   2
   fizz
   4
  buzz
    
    const fizzBuzz = (nums) => {
      for (let i = 1; i <= nums; i++) {
        if (i % 3 === 0 && i % 5 === 0) {
          console.log("fizzBuzz")
        } else if (i % 5 === 0) {
          console.log("buzz")
        } else if (i % 3 === 0) {
          console.log("fizz")
        } else {
          console.log(i)
        }
      }
    }
    
    
### 8. // Write a function that returns the provided string with the first letter of each word capitalized. Make sure the rest of the word is in lower case.
 --- Examples
capitalize("I'm a little tea pot") --> 'I'm A Little Tea Pot'
capitalize('sHoRt AnD sToUt') --> 'Short And Stout'

    const fisrtStr = (str) => {
      let split = str.split(" ")
      for (let i = 0; i < split.length; i++) {
        split[i] = split[i][0].toUpperCase() + split[i].substring(1).toLowerCase()

      }

      return split.join(" ")
    }


### 9. Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

    function isAnagram(s: string, t: string): boolean {
        let letters = {}

        if(s.length !== t.length){
            return false
        }
        for (let i = 0; i < s.length; i++){
            letters[s[i]] = letters[s[i]]+1 || 1
        }

        for (let i = 0; i < t.length; i++){
            if(!letters[t[i]] ){
                return false
            }else{
                letters[t[i]]--
            }
        }
        return true
    };
    
### 10.  Write a function that accepts a positive number N. The function should console log a pyramid shape with N levels using the # character.  Make sure the
             pyramid has spaces on both the left and right side
             --- Examples
               pyramid(1)
                   '#'
               pyramid(2)
                   ' # '
                   '###'
               pyramid(3)
                   '  #  '
                  ' ### '
                  '#####'
                  
                  
            const pyramid = (n) => {
              for(let i = 0; i<n; i++){
                const padding = " ".repeat(n-i)
                const hash = "#"
                console.log(padding + hash.repeat(i+1) + padding)

              }
            }


### 11.  Write a function that returns the number of vowels found within a string. Vowel characters are 'a', 'e', 'i', 'o', and 'u'.
Make sure the function is case insensitive!
         --- Examples
           vowels('What') --> 1
          vowels('Why?') --> 0
           vowels('aEiOu') --> 5
          vowels('I am a world-class developer using iterations') --> 16
        
        
            const vowels = {
              "a" : "a",
              "e" : "e",
              "i" : "i",
              "o" : "o",
              "u" : "u"
            }

        const vowelsNum = (str) => {
          let count = {}
          let total = 0
          for(let i=0; i < str.length; i++){

            if(vowels[str[i].toLowerCase() ] == str[i].toLowerCase() ){
              count[str[i]] = count[str[i]]+1 || 1

            }
          }

          for(let x in count){
            total += count[x]
          }
          console.log(total)
        }
  solution 2

	  const numberOfVowels = (s) => {
		  const vowels =  ['a','e','i','o','u']
		  let count = 0
		  for (let i = 0; i < s.length; i++){
		    if(vowels.includes(s[i].toLowerCase())){
		      count++
		    }
	  }
	
	  return count
	}

 
### Sorting algorithms 

    // sorting algorithm (Bubble sort)

        const srt = (arr) => {

          for (let i = 0; i < arr.length; i++) {
            for (let j = 0; j < arr.length; j++) {

              if (arr[j] > arr[j + 1]) {
                let temp = arr[j]
                arr[j] = arr[j + 1]
                arr[j + 1] = temp

              }
            }
          }
          console.log(arr)
        }
        
<!--       Bubble sort with do-while   -->

        const bubbleSort = (arr) => {
          let swapped 
          do{
            swapped  = false
              for(let j = 0 ;j < arr.length; j++ ){
              if(arr[j] > arr[j + 1]){
                let temp = arr[j]
                arr[j] = arr[j+1]
                arr[j+1] = temp
                swapped = true
              }
            }
          }while(swapped)


          return arr
        }

        //  sorting algorithm (Selection sort)

        const sltSrt = (arr) => {
          for (let i = 0; i < arr.length; i++) {
            let swapIndex = i
            for (let j = i + i; j < arr.length; j++) {
              if (arr[j] < arr[swapIndex]) {
                swapIndex = j

              }
            }
            let sve = arr[swapIndex]
            arr[i] = arr[swapIndex]
            arr[i + 1] = sve
          }

          console.log(arr)
        }
        
### Linked List

    class Node {
      constructor(val, n) {
        this.val = val
        this.n = n
      }
    }

    class LinkedList {
      constructor() {
        this.head = null
        this.length = 0
      }
      unShift(data) {
        const newNode = new Node(data, this.head)
        this.head = newNode
        this.length++
      }

      getFirst() {
        return this.head
      }

      getLast() {
        let currentNode = this.head
        while (currentNode && currentNode.next) {
          currentNode = currentNode.next


        }
        return currentNode
      }

      getLength(){
        return this.length
      }

      clear(){
        this.head = null
        this.length = 0
      }


    }
    
### Queues

    class Queue {
      constructor(){
        this.data = []
      }

      enQueue(val){
        this.data.unshift(val)
      }

      deQueue(){
        this.data.pop()
      }
    }
    
### Implementing graphs

    const nodes = ['a', 'b', 'c', 'd', 'e']

    const edges = [
      ['a', 'b'],
      ['a', 'd'],
      ['d', 'c'],
      ['d', 'e'],
      ['c', 'b'],
      ['c', 'e']
    ]

    const findAdjacentNodes = (node) => {
      let adjacents = []
      for (let i = 0; i < edges.length; i++) {
        const nodeIdx = edges[i].indexOf(node)
        if (nodeIdx > -1) {
          const adjacentNode = nodeIdx === 0 ? edges[i][1] : edges[i][0]
          adjacents.push(adjacentNode)
        }
      }

      return adjacents
    }

    const isConnected = (node1, node2) => {
      for (let i = 0; i < edges.length; i++) {
        if (edges[i].includes(node1) && edges[i].includes(node2)) {
          return true
        }
      }

      return false
    }


        
### 12.  Create a function that when given 2 sorted arrays, it returns a new sorted array that contains both elements of input arrays
 --- Examples merge([1,3], [2,4]) === [1,2,3,4] 
 merge([1,5], [4,6,7]) === [1,4,5,6,7]
 merge([4,6,7], [1,5]) === [1,4,5,6,7]
 
 
     const mergeSortedArr = (arr1,arr2) => {
      const newArr = arr1.concat(arr2)

      for (let i = 0; i < newArr.length; i++){
        for (let j = 0; j < newArr.length; j++){
          if(newArr[j] > newArr[j + 1]){
            let sve = newArr[j]
            newArr[j] = newArr[j + 1]
            newArr[j+1] = sve
          }

        }
      }

      return newArr


    }
    
### 13. No duplicates. Given  a string, return true if every character appears once, and return false otherwise. Can you solve this without returning any additional    data structure. 

    solution 1
    
    const noDuplicates = (str) => {
      for (let i = 0; i < str.length; i++){
        for (let j = i+1; j < str.length; j++){
          if(str[i] === str[j]){
            return false
          }
        }
      }
      return true
    }
    
    solution 2
    
    const noDuplicates = (str) => {
      const spt = str.split("").sort().join("")
      for (let i = 0; i < spt.length; i++) {
        if (spt[i] === spt[i + 1]) {
          return false
        }
      }

      return true

    }

### 14. Given a string, return a new string with all spaces replaced with '%20'. 

    const replaceString = (str) => {
      let store = []
      for (i in str) {
        if (str[i] === " ") {
          store.push("%20")
        }
        else {
          store.push(str[i])
        }
      }

      return res = store.join("")

    }

### 15. Given an input string, write a function that returns a compressed string exactly as seen below. 
        bbcdddddbbb -> 2bc1d5b3
        If the compresses string is not smaller than the original string, return the original string.
        
        const compressString = (str) => {
          let compressed = ""
          let counter = 1
          for (let i = 0; i < str.length; i++) {
            if (str[i] === str[i + 1]) {
              counter++
            }else{
              compressed = compressed + str[i] + counter.toString()
              counter = 1
            }
          }

          return compressed
        }
        
### 16. Given an array of sorted numbers and a target sum, find a pair in the array whose sum is equal to the given target. E.g array = [1,2,3,4,5] targetSum = 7. 

        const findPair = (arr,p) => {
          let leftCounter = 0,
            rightCounter = arr.length - 1
            let pair = null
          while(leftCounter != rightCounter){
            pairSum = arr[leftCounter]+arr[rightCounter]
            if(pairSum === p){
            pair = [ arr[leftCounter],arr[rightCounter]]
            }
            else if(pairSum < p){
              leftCounter++
            }else if(pairSum > p){
              rightCounter--
            }
          }

          return pair

        }
        
 ### 17. Given an array of integers, return an array such that such that product[i] is equal to the product of all the elements of arr[i]. Solve without division operation in o(n) time complexity. 
 
 
     `const productOfAllOtherNumbers = (arr) => {
      let beforeProductsSoFar = 1
      const productsOfBeforeNumbers = []
      for (let i = 0; i < arr.length; i++) {
        productsOfBeforeNumbers[i] = beforeProductsSoFar
        beforeProductsSoFar *= arr[i]
      }


      let afterProductsSoFar = 1
      const productsOfAfterNumbers = []
      for(let j = arr.length - 1; j > -1; j--){
        productsOfAfterNumbers[j] = afterProductsSoFar;
        afterProductsSoFar *= arr[j]
      }

      const products = []
      for (let k = 0; k < arr.length; k++){
        products[k] = productsOfAfterNumbers[k] * productsOfBeforeNumbers[k]
      }

      return products
    }`
    
### 18. Implementing binary search. 
    
    const binarySearch = (arr, targetValue) => {
      let leftCounter = 0
      let rightCounter = arr.length - 1

      while (leftCounter <= rightCounter) {
        let mid = Math.floor((leftCounter + rightCounter) / 2)

        if (arr[mid] === targetValue) {
          return arr[mid]
        } else if (targetValue < arr[mid]) {
          rightCounter = mid - 1
        } else {
          leftCounter = mid + 1
        }

      }
      return false
    }
    
### 19. /*
    Task - recreate the browser’s native setInterval() function without using window.setInterval() itself

     A) Create as a SetInterval prototype, that takes two constructor arguments:
        1. "func", the function to be called at the intervals
        2. "interval", the amount of time in milliseconds between each interval


       B) Create "clear" method on SetInterval that will clear the intervals from running

       Reference - https://www.w3schools.com/jsref/met_win_setinterval.asp
    */

    function SetInterval(func, interval) {
      this.func = func
      this.interval = interval
      this.start()

    }


    SetInterval.prototype.start = function() {
      this.timer = setTimeout(()=>{
        this.func()
        this.start()
      },1000)
    }

    SetInterval.prototype.clear = function() {
       clearInterval(this.timer)
    }


    /* Do not edit below this line and don’t create any additional functions */

    var myInterval = new SetInterval(() => {console.log("Bryan!");}, 1000);
    setTimeout(() => myInterval.clear(), 6000);

### 18. Cartesian product.

    const catersian = (a,b) => {
      let res = []
      for(let i = 0; i < a.length; i++) {
        for(let j = 0; j < b.length; j++){
          res.push([a[i],b[j]])
        }
      }

      console.log(res)
    }

### 19. Fibonnaci sequence - 

    1.
    const solution = (n) => {
      let arr = []
      for(let i = 0; i <= n - 1 ; i++){
      	if( i == 0 || i == 1){
        	arr.push(i)  
        }else{
        	arr.push(arr[i-1] + arr[i-2])
          
        }
        
      }
      return arr
    }

    2.
    const finobacci = (n) => {
    	let arr = [0,1]
          for (let i = 2; i < n; i++ ){
            arr[i] = arr[i - 1] + arr[ i - 2]
            
          }
          
          return arr
    }

### 20 Factoria of a number
    const factoria = (n) => {
    	let a = 1
    	for (let i = 1; i <= n; i++){
      	if(i > 0){
        	a *= i
          
        }
      }
      return a
    
    }

### 21 Is prime number
    const isPrime = (n) => {
      if (n  < 2) {
        return false
      }
    
      if (n % 2 == 0) {
        return false
      }
    
      return true
    }

### 22 Power of two
    solution 1 - 0(n)
    const powerOfTwo = (n)=> {
	let a = 0
      while( a < n){
      	if( n == 2 ** a){
        	return true
        }
        a++
      }
      return false
    }

    solution 2 - 0(logn)
    const powerOfTwo = (n) => {
	  if (n < 1) {
	    return false
	  }
	  while (n > 1) {
	    if (n % 2 !== 0) {
	      return false
	    }
	    n = n / 2
	  }
	  return true
	}

### 23. Recursive Finobacci
	const recursiveFactorial = (n) => {
	  if (n < 1) return 1
	  return n * recursiveFactorial(n - 1)
	}

### 24. Recursive binary search
	 const rbs = (arr, target) => {
  return search(arr,target,0,arr.length - 1)
 }

const search = (arr,target,leftIndex,rightIndex) => {
  if( leftIndex > rightIndex ){
    return -1
  }

  let mid = Math.floor((leftIndex + rightIndex) / 2)
   if( arr[mid] === target){
     return mid
   }else if(target  > arr[mid]){
     return search(arr, target, mid + 1,rightIndex)
   }else{
     return  search(arr, target, leftIndex,mid - 1)
   }


}

### 25. Quick sort

	const quickSort = (arr) => {
		if(arr.length < 2) return arr
	  let pivot = arr[0],
	    left = [],
	    right = []
	
	  for( let i = 1; i < arr.length; i++  ){
	  	if(arr[i] < pivot){
	    	left.push(arr[i])
	    }else{
	    right.push(arr[i])
	    }
	  }
	  
	  return [...quickSort(left),pivot,...quickSort(right)]
	}
### 26. Merge sort
	const mergeSort = (arr) => {
	  if (arr.length < 2) return arr
	  let mid = Math.floor(arr.length/2),
	    left = arr.slice(0,mid),
	    right = arr.slice(mid)
	
	  return merge(mergeSort(left), mergeSort(right))
	}
	
	const merge = (left, right) => {
	  let sortedArr = []
	  while (left.length && right.length) {
	    if (left[0] > right[0]) {
	      sortedArr.push(right.shift())
	    } else {
	      sortedArr.push(left.shift())
	    }
	  }
	
	  return [...sortedArr, ...left, ...right]
	}

 ### 27. Climbing stairs
	  const climbingStairs = (n) => {
	 	const numberOfWays = [1,2]
	  for (let i = 2; i < n; i++){
	  	numberOfWays[i] = numberOfWays[ i - 2 ] + numberOfWays[ i - 1]
	  }
	  
	  return numberOfWays[n - 1]
	 }


### 28. Two sums
	const twoSums = (arr,target) => {
	let storage = {}
	  
	  for (let i = 0; i < arr.length; i++){
	  	if(storage[arr[i]] !== undefined){
	    	return [ storage[arr[i]], i ]
	    }
	    storage[target - arr[i]] = i
	  }
	}

### 29. Reverse integer with range [-2^31, 2^31 -1] 

	const reverseInteger = (n) => {
	  if (n < 0) {
	    return -1 * Number((-1 * n + "").split('').reverse().join(""))
	  }
	  const result = Number((n+"").split('').reverse().join(""))
	  return result > ((2** 31) - 1) ? 0 : result
	}

### 30. Assign cookies
	const assignCookies = (g,s) => {
	let satisfied = 0
	s.sort((a,b)=> a - b)
	  g.sort((a,b)=> a-b)
	  
	  for ( let i = 0; i < s.length; i++ ){
	  	if( s[i] >= g[i] ){
	    	satisfied++
	    }
	  }
	  
	  return satisfied
	}

 ### 31. Maximum subarray
 	const longestSubarray = (arr) => {
	let solution = arr[0]
  
	  for (let i = 1; i < arr.length; i++){
	  console.log(solution)
	  	arr[i] = Math.max(arr[i], arr[i] + arr[i - 1]);
	    solution = Math.max(solution,arr[i])
	    
	    
	  }
	  return solution
	}


### 32. Find minimum in rotated sorted array.
	const minimumRotatedSortedArray = (arr)=> {
	  let left = 0,
	    right = arr.length - 1
	   
	
	  while (left < right){
	    let mid = Math.floor((left+right)/2)
	   
	    if(arr[mid] > arr[right]){
	      left = mid+1
	    }else{
	      right = mid
	    }
	  }
	
	  return arr[right]
	}

 ### 33. 

 React test
 https://codesandbox.io/p/sandbox/messages-forked-mnfm3z?file=%2Fsrc%2FuseWithMessages.js%3A55%2C7



### 34.
Roman to integer

```
/**
 * @param {string} s
 * @return {number}
 */
var romanToInt = function(s) {
    const romanToValue = {
        I : 1,
        V : 5,
        X : 10,
        L : 50,
        C : 100,
        D : 500,
        M : 1000
    }


    let total = 0

    for (let i = 0; i < s.length; i++){
        if(romanToValue[s[i]] < romanToValue[s[i+1]]){
            total -= romanToValue[s[i]]
        }else{
            total += romanToValue[s[i]]
        }
    }

    return total
    
};
```

### 35. Longest common prefix

```
function longestCommonPrefix(strs) {
    if (strs.length === 0) return "";

    // Start with the prefix being the first string
    let prefix = strs[0];

    // Compare the prefix with each string in the array
    for (let i = 1; i < strs.length; i++) {
        // Check the current string against the prefix
        while (strs[i].indexOf(prefix) !== 0) {
            // Reduce the prefix by one character from the end
            prefix = prefix.slice(0, prefix.length - 1);
            // If the prefix is reduced to an empty string, return ""
            if (prefix === "") return "";
        }
    }

    return prefix;
}



```

### 36. Valid parenthesis

```
var isValid = function(s) {

    let stack = []

    const bracketsToEnd = {
        ')': '(',
        '}': '{',
        ']': '['
    };

    for (char of s){
        // check if item is a closing element . e.g ),],}
        if(char in bracketsToEnd ){
            // store end of stack temporarily
            const topElement = stack.pop()
            if(topElement !== bracketsToEnd[char]) return false
        }else{
            stack.push(char)
        }
    }

    return stack.length === 0
};
```

### 37. Max profit
```
ar maxProfit = function(prices) {
    let minPrice = Infinity,
        maxProf = 0

    for (let i = 0; i < prices.length; i++) {
        if (prices[i] < minPrice) {
            minPrice = prices[i]
        }else{
           const profit =  prices[i] - minPrice

            if(profit > maxProf){
                maxProf = profit
            }
        }
    }

    return maxProf
};
```

### 38. Max subarray
```
	var maxSubArray = function(nums) {
    let maxCurrent = nums[0],
        maxGlobal = nums[0]

    for (let i = 1; i < nums.length; i++){
        maxCurrent = Math.max(nums[i], nums[i] + maxCurrent)

        if(maxCurrent > maxGlobal){
            maxGlobal = maxCurrent
        }
    }

    return maxGlobal
};
```

### 39. First unique character in string

```
var firstUniqChar = function(s) {
    let store = {}

    for (let i = 0; i < s.length; i++){
        store[s[i]] = store[s[i]] ? store[s[i]] + 1 : 1
    }

    for (let i = 0; i < s.length; i++){
        if(store[s[i]] === 1){
            return i
        }
    }

    return -1
};
```

### 40. Group anagrams
```
const groupAnagrams = (s) => {
    let groups = {

    }

    for(let i = 0; i < s.length; i++){
        const key = s[i].split('').sort().join('')
        if(key in groups){
            groups[key].push(s[i])
        }else{
            groups[key] = [s[i]]
        }
    }

   

    return Object.values(groups)
}
```

### 41. Reactjs Letter Tile (Coderbyte_ 
![alt text](https://media.studyx.ai/us/6bad6d39/be60b276de0d48c4b9580ccda1e7a439.jpg)

```
import React, { useState } from 'react';
import { createRoot } from 'react-dom/client';

const style = {
  letterContainer: {
    overflow: 'auto',
    marginBottom: '10px'
  },
  letter: {
    float: 'left',
    padding: '10px 10px',
    background: '#c9e4ed',
    borderRadius: '5px',
    marginRight: '5px',
    cursor: 'pointer'
  }
};

function Tile(props) {
  return (
    <button onClick={() => {
      props.onClick(props.letter)
    }}  style={style.letter}>{ props.letter }</button>
  );
}

function App(props) {

  const [letters,setLetters] = useState('')

  const alph = Array.from({ length: 26 }, (_, i) =>
    String.fromCharCode(65 + i)
  );

  const handleClick = (l) => {

    const a = letters[letters.length - 2]
    const b = letters[letters.length - 1]

    if (l == a && l == b) {
      const p = letters.slice(0, letters.length - 2)
        setLetters(p+"_")
    } else {
       setLetters(letters + l)
    }
  
   
  }

  return (
    <section>
      <aside style={style.letterContainer} id="letterContainer">
        {
          alph.map((item, index) => (
            <Tile letter={item} onClick={(e) => {
              handleClick(e)
            }}  />
          ))
       }
      </aside>
      <div id="outputString">{letters}</div>
    </section>
  );
}

export default App
```

### 42  Merge Two Sorted Lists

```
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} list1
 * @param {ListNode} list2
 * @return {ListNode}
 */
var mergeTwoLists = function(list1, list2) {
    let curr = new ListNode()
    const dummy = curr
    while (list1 && list2){
        if(list1.val < list2.val){
            curr.next = list1
            list1 = list1.next
        }else{
            curr.next = list2
            list2 = list2.next
        }
        curr = curr.next
    }

    if(list1){
        curr.next = list1
    }

    if(list2){
        curr.next = list2
    }

    return dummy.next
};

```

### 43 Remove element
```
/**
 * @param {number[]} nums
 * @param {number} val
 * @return {number}
 */
var removeElement = function (nums, val) {
    let right = 0
        left = 0
    
    while(right < nums.length){
        if (nums[right] !== val){
            nums[left] = nums[right]
            left++
        }
        right++
    }

    return left

};
```
