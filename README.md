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
