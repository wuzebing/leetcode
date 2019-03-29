Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].


```
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    if(nums == null || nums.length < 2) return [-1,-1];
    
    let result = [-1,-1];
    let map = {};
    for(let i=0;i<nums.length;i++){
        let num = nums[i];
        if(map[target-num] != undefined){
            result = [map[target-num],i];
            break;
        }
        map[num] = i;
    }
    return result;    
};
```