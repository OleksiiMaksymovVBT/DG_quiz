# Intersection

## Task

Given two arrays of numbers where each one contains unique values and is already sorted in ascending order, find the number of elements that belong to both arrays.

`int intersectionCount(int[] a, int[] b)`

## Solution

```typescript
function intersectionCount(a: number[], b: number[]): number {
    let numberOfIntersections = 0,
        aIndex = 0,
        bIndex = 0; 

    while ( aIndex < a.length && 
            bIndex < b.length) {
        if (a[aIndex] === b[bIndex]) {
            numberOfIntersections++;
            
            aIndex++;
            bIndex++;
        } else if (a[aIndex] < b[bIndex]) {
            aIndex++;
        } else {
            bIndex++;
        }
    }

    return numberOfIntersections;
}


console.log(intersectionCount(
[1,3,4,5,7],
[2,3,5,6]
));

console.log(intersectionCount(
[2,4,6,8],
[1,3,5,7]
));

console.log(intersectionCount(
[1,2,3,4,5,7],
[1,2,3,4,5,7]
));

/*
Rsult
2
0
6
*/

```