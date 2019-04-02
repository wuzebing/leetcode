Given a string s, find the longest palindromic substring in s. You may assume that the maximum length of s is 1000.

Example 1:

Input: "babad"
Output: "bab"
Note: "aba" is also a valid answer.
Example 2:

Input: "cbbd"
Output: "bb"

```
/**
 * @param {string} s
 * @return {string}
 */
var res = "";

var longestPalindrome = function(s) {
    if(s == null || s.length <= 0) return;
    
    for(var i=0;i<s.length;i++){
        help(s, i, i);
        help(s, i, i+1);
    }
    return res;
};

function help(source,left,right){
    while(left>=0 && right<source.length && source[left] == source[right]){
        left--;
        right++;
    }
    var str = source.substring(left+1,right);
    if(str.length > res.length){
       res = str;
    }
}
```