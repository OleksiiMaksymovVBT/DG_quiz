# Palindrome check

## Task

Write an efficient function that checks whether any permutation of an input string is a palindrome. Note that the function is not a palindrome check (see example 2).

Examples:

- "civic" should return True
- "ivicc" should return True  (because “civic” is a permutation of “ivicc”)
- "civil" should return False
- "livci" should return False

`bool isPalindromable(string s) `

## Solution

```typescript
function isPalindromable(s: string): boolean {
    const charCountHashMap: Record<string, number> = {};

    // saving amount of chars fromstring to hash map
    let len = s.length;
    for (let i = 0; i < len; i++) {
        charCountHashMap[s[i]] = (charCountHashMap[s[i]] || 0) + 1;
    }

    // to have it palindromable we should have MAX 1 char odd amount
    let oddChars = 0;
    for (const charCount of Object.values(charCountHashMap)) {
        if (charCount % 2 !== 0) {
            if(++oddChars > 1) return false
        }
    }
    return true;
}

console.log(isPalindromable("civic"));  
console.log(isPalindromable("ivicc"));  
console.log(isPalindromable("civil"));   
console.log(isPalindromable("livci"));  

/*
res:
true
true
false
false
*/
```