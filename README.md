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
    
### 2. Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

    You must implement a solution with a linear runtime complexity and use only constant extra space.
    
    function singleNumber(s: number[]): number {
        let ans = []
        for(let i = 0; i < s.length; i++){
            for(let j = i + 1; j < s.length; j++){
                if(s[j] === s[i]){
                ans.push(s[i])
              }
            }
        }

      const res = s.filter(x => !ans.includes(x));
      return  Number(res.join()) 
    };
    
    
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

    var lengthOfLastWord = function(word) {
        const sw = word.split(" ")
        const fil = sw.filter((i => i !== ""));
        const lastWord = fil[fil.length - 1].length;

        return lastWord; 
    };

### 5. Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

    A subarray is a contiguous part of an array.
    
    var maxSubArray = function(nums) {
    let currentNumber = 0;
    let maxSum = -Infinity
  
  
    for (let i = 0; i < nums.length; i++){
      currentNumber = Math.max(nums[i], currentNumber + nums[i])
          maxSum = Math.max(maxSum, currentNumber )
    }
    
    return maxSum
    
    };
    
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
    
## 8. Write a program that console logs the numbers from 1 to n. But for multiples of three print ???fizz??? instead of the number and for the multiples of five print ???buzz???. For numbers which are multiples of both three and five print ???fizzbuzz???.
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



