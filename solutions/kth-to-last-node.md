# K-th to last node

## Task 

Write a function that takes a head node of a singly linked list (containing at least k+1 elements), and returns kth element to the last node in the list. 

`kthToLastNode(LinkedListNode head, int k)`

## Solution

```typescript
class LinkedListNode {
    next: LinkedListNode | null;
    constructor(public val: number) {
        this.next = null;
    }
}

function kthToLastNode(head: LinkedListNode, k: number) {
    // we now that k is at least 0 by task, so no checks here...
    let laggard: LinkedListNode | null = head;
    let runner: LinkedListNode | null = head;

    // move runner k nodes ahead
    for (let i = 0; i < k; i++) 
        runner = runner.next;
        // no check, because we believe in Task given values :D 

    // move both pointers until the runner pointer reaches the end
    while (runner !== null && runner.next !== null) {

        runner = runner.next;
        laggard = laggard!.next;

    }

    // laggard pointer is now at the kth to the last node
    return laggard;
}

const head = new LinkedListNode(0);
let itterable = head;
[1,2,3,4,5,6,7,8,9,10].forEach(n => {
    itterable.next = new LinkedListNode(n);
    itterable = itterable.next;
});

console.log(kthToLastNode(head, 2));
console.log(kthToLastNode(head, 4));
console.log(kthToLastNode(head, 6));
console.log(kthToLastNode(head, 8));
/**
 * Result of running
LinkedListNode {
  val: 8,
  next: LinkedListNode {
    val: 9,
    next: LinkedListNode { val: 10, next: null }
  }
}
LinkedListNode {
  val: 6,
  next: LinkedListNode {
    val: 7,
    next: LinkedListNode { val: 8, next: [LinkedListNode] }
  }
}
LinkedListNode {
  val: 4,
  next: LinkedListNode {
    val: 5,
    next: LinkedListNode { val: 6, next: [LinkedListNode] }
  }
}
LinkedListNode {
  val: 2,
  next: LinkedListNode {
    val: 3,
    next: LinkedListNode { val: 4, next: [LinkedListNode] }
  }
}
*/
```