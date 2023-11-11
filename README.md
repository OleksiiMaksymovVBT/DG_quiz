# Datagrok Quiz
Use a language of your choice (Python / C++ / C# / Java / JavaScript / Dart) to solve the following problems. Use the most efficient algorithm you can think of. The code doesn’t have to be compilable, so just include a relevant code snippet. Refrain from using built-in functions that directly solve the problem. Do not bother to check input parameters. Pseudocode is fine. Add comments or thoughts if you want. Include solutions right in the document, on the same page with the problem statement. You may take pictures and insert them in the document for graphical problems.

Please designate 2 hours of uninterrupted time, and try to solve as many problems as possible on your own. Do not google solutions or use the Internet. Do not worry if you do not solve them all, or run out of time – we will be discussing them in the follow-up interview.


## Sum up a binary tree

Given a binary tree, write a function that returns the sum of the values of that tree.
```
class Node {
  Node left;  // left node, or null 
  Node right;  // right node, or null
  double value;
},
```
`double sum(Node root)`


## Find an area of the intersection of two rectangles

```
class Rect {
  double x, y, width, height;   
  // you can use x1, y1, x2, y2 properties, too
}
```
`double intersectionArea(Rect r1, Rect r2)`

## Palindrome check

Write an efficient function that checks whether any permutation of an input string is a palindrome. Note that the function is not a palindrome check (see example 2).

Examples:

- "civic" should return True
- "ivicc" should return True  (because “civic” is a permutation of “ivicc”)
- "civil" should return False
- "livci" should return False

`bool isPalindromable(string s) `
## K-th to last node

Write a function that takes a head node of a singly linked list (containing at least k+1 elements), and returns kth element to the last node in the list. 

`kthToLastNode(LinkedListNode head, int k)`

## Duplicates

In an array of integers of length n + 1 (n > 1), every number in the range 1...n appears once except for one number which appears twice (so the array’s length is n+1). Write an efficient function that finds the number that appears twice.

Examples:

- 1,2,2,3 => 2 
- 1,2,3,3 => 3
- 2,1,4,3,5,4 => 4

`int findDuplicate(int[] values)`

## Intersection

Given two arrays of numbers where each one contains unique values and is already sorted in ascending order, find the number of elements that belong to both arrays.

`int intersectionCount(int[] a, int[] b)`

## RLE encoder 

Given a string of letters (without numbers), create a string encoding it by the rules where the first character is char itself, followed by a number indicating the number of letter repeats.

Examples:

- ABBA => A1B2A1
- ATTTGC => A1T3G1C1

`string rle(string s)`

## Search insert position

Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order. Is it possible to write an algorithm with O(log n) runtime complexity?

Examples:

- Input: values = [1,3,5,6], target = 7. Output: 4
- Input: values = [1], target = 0. Output: 0

`int findIndex(int[] values, int target)`


## Complexity

What is the complexity of the following functions (assuming they are implemented efficiently):

- max(double[] values)
- sort(double[] values)
- avg(double[] values)
- median(double[] values)
- stdev(double[] values)
- uniqueValuesCount(byte[] values)


## Achiver

Is it possible to develop an archiver that would compress every possible file bigger than 1GB by at least one byte? Provide your reasoning.

