# Sum up a binary tree

## Task 

Given a binary tree, write a function that returns the sum of the values of that tree.
```
class Node {
  Node left;  // left node, or null 
  Node right;  // right node, or null
  double value;
},
```
`double sum(Node root)`

## Solution

```typescript
class Node {
  left: Node;  // left node, or null 
  right: Node;  // right node, or null
  value: number; // double doesn't exist for TS

  contstructor(_value: number) {
    // some error throwing checks can go here.. 
    if(isNaN(_value)) throw new Error('Fooo');
    this.value = _value;
    return this;
  }

  left(_left: Node) {
    this.left = _left;
    return this;
  }


  right(_right: Node) {
    this.right = _right;
    return this;
  }

  summ() {
    let summVal = 0;
    return (this.value + this.left.summ() + this.right.summ());
  }
}

const ll = new Node(5);
const lr = new Node(6);
const l = new Node(7).left(ll).right(lr);

const rl = new Node(8);
const rr = new Node(9);
const r = new Node(10).left(rl).right(rr);

const root = new Node(11).left(l).right(r);


function getSumm(root: Node) {
    return root.summ()
}
// result
const summ1 = getSumm(root);
// or just
const summ2 = root.summ();
// or even like this..., if we don't have any summ function inside the Class
summ(root: Node) {
    if (root == null) 
        return 0;  
    
    const leftSum = sum(root.left);
    const rightSum = sum(root.right);

    return root.value + leftSum + rightSum;    
}
const summ3 = summ(root);
```

## Notes
### Compexity
- Time Complexity: The time it takes for the sum function to calculate the sum in this binary tree is proportional to the number of nodes, denoted as N. So, we express its time complexity as O(N). This is because, in the worst-case scenario, the function has to go through each and every node in the tree at least once to compute the sum.
- Space Complexity: The space required by the function is also linked to the number of nodes, leading to a space complexity of O(N). The recursion in the function contributes to the space complexity. In the worst case, the number of recursive calls on the call stack is O(h), where h is the height of the binary tree and can be up to N (->O(N))
### Variable type limitations
- The limiation in max value of the double. It always can reach the ceiling, beucase by the task given we have both Node.value and result of the function summ as *double*. So max floating point value for 8 bytes.
- As here we used recursion method, we can reach max call stack. The max value of calls depends on the platform/language/etc, but in applied tasks this number is human-reachable (less than 1k) 
