# DSA

###  Given an integer x, return true if x is palindrome integer.

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
    
### Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

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
    
    
### Implement strStr().

    Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

    Clarification:

    What should we return when needle is an empty string? This is a great question to ask during an interview.

    For the purpose of this problem, we will return 0 when needle is an empty string. This is consistent to C's strstr() and Java's indexOf().
    
    
    ## solution
    function strStr(haystack: string, needle: string): number {
    	const index = haystack.indexOf(needle)
  
 	    return index

    };
    
    
    ### Given a string s consisting of some words separated by some number of spaces, return the length of the last word in the string.

        A word is a maximal substring consisting of non-space characters only.
        
        var lengthOfLastWord = function(word) {
            const sw = word.split(" ")
            const fil = sw.filter((i => i !== ""));
            const lastWord = fil[fil.length - 1].length;

            return lastWord; 
        };
