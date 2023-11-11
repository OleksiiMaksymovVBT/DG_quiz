# Search insert position

## Task

Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order. Is it possible to write an algorithm with O(log n) runtime complexity?

Examples:

- Input: values = [1,3,5,6], target = 7. Output: 4
- Input: values = [1], target = 0. Output: 0

`int findIndex(int[] values, int target)`

## Solution

```typescript
function findIndex(values: number[], target: number) {
    let leftPointer = 0, rightPointer = values.length - 1;

    while (rightPointer >= leftPointer) {
        const mid = Math.floor(leftPointer + (rightPointer - leftPointer) / 2);
        if (values[mid] === target) {
            //found
            return mid;
        } else if (values[mid] < target) {
            //search in right half
            leftPointer = mid + 1;
        } else {
            // or in the left half
            rightPointer = mid - 1;
        }
    }

    //index where it has to be inserted
    return leftPointer;
}


console.log(findIndex([1,3,5,6], 7));
console.log(findIndex([1], 0));
console.log(findIndex([1], 2));
console.log(findIndex([1,2,4], 3));
console.log(findIndex([1,2,4], 2));

/*
Res:
4
0
1
2
1
*/
```