# Duplicates


## Task

In an array of integers of length n + 1 (n > 1), every number in the range 1...n appears once except for one number which appears twice (so the array’s length is n+1). Write an efficient function that finds the number that appears twice.

Examples:

- 1,2,2,3 => 2 
- 1,2,3,3 => 3
- 2,1,4,3,5,4 => 4

`int findDuplicate(int[] values)`

## Solution

```typescript
function findDuplicate(values: Array<number>): number {
    const hashMapOfNumber: { [key: number]: boolean } = {};

    const len = values.length;
    for (let i = 0; i< len; i++>) {
        if (hashMapOfNumber[values[i]]) {
            return values[i];
        } else {
            hashMapOfNumber[values[i]] = true;
        }
    }

    return -1; // No duplicate found
}

console.log(findDuplicate([1,2,2,3]));
console.log(findDuplicate([1,2,3,3]))
console.log(findDuplicate([2,1,4,3,5,4]));
/**
 Result
 2
 3
 4
 * /


```

