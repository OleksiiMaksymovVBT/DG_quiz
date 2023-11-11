# RLE Encoder

## Task

Given a string of letters (without numbers), create a string encoding it by the rules where the first character is char itself, followed by a number indicating the number of letter repeats.

Examples:

- ABBA => A1B2A1
- ATTTGC => A1T3G1C1

`string rle(string s)`

## Solution


```typescript
function rle(s: string){
    let res = "";
    let currentChar = s[0];
    let currentCharCounter = 1;
    const strLen = s.length;
    for (let i = 1; i <= strLen; i++) {
        if (currentChar!==s[i]) {
            res += currentChar + currentCharCounter;
            currentChar = s[i];
            currentCharCounter = 1;
        } else currentCharCounter++;
    }

    return res;
}


console.log(rle("ABBA"));    
console.log(rle("ATTTGC"));  

/*
Result:
A1B2A1
A1T3G1C1
*/
```
