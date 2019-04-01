Given a string, find the length of the longest substring without repeating characters.

Example 1:

Input: "abcabcbb"
Output: 3 
Explanation: The answer is "abc", with the length of 3. 
Example 2:

Input: "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
Example 3:

Input: "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3. 
             Note that the answer must be a substring, "pwke" is a subsequence and not a substring.

```
/**
 * @param {string} s
 * @return {number}
 */
var lengthOfLongestSubstring = function(s) {
    if(s == null || s.length <= 0) return 0;
    
    var res = 0;
    var arr = [];
    for(var i=0,j=0;i<s.length;i++){
        if(arr.indexOf(s[i]) > -1){
             arr.splice(j,arr.indexOf(s[i])+1)
        }
        arr.push(s[i]);
        res = Math.max(res,arr.length)
    }
    
    return res;
};

```