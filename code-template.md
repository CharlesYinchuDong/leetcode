### Backtracking

LeetCode Problems:
- [93. Restore IP Addresses](https://leetcode.com/problems/restore-ip-addresses/)
- [78. Subsets](https://leetcode.com/problems/subsets/)
- [90. Subsets II](https://leetcode.com/problems/subsets-ii/)
- [46. Permutations](https://leetcode.com/problems/permutations/)
- [47. Permutations II](https://leetcode.com/problems/permutations-ii/)
- [39. Combination Sum](https://leetcode.com/problems/combination-sum/)
- [40. Combination Sum II](https://leetcode.com/problems/combination-sum-ii/)
- [131. Palindrome Partitioning](https://leetcode.com/problems/palindrome-partitioning/)
- [842. Split Array into Fibonacci Sequence](https://leetcode.com/problems/split-array-into-fibonacci-sequence/)

Graph traversal
- [332. Reconstruct Itinerary](https://leetcode.com/problems/reconstruct-itinerary/)
- [207. Course Schedule](https://leetcode.com/problems/course-schedule/)
- [210. Course Schedule II](https://leetcode.com/problems/course-schedule-ii/)

Game Playing
- [464. Can I Win](https://leetcode.com/problems/can-i-win/)

Template:
```py
class Solution(object):
    def algorithm(self, s):
        res = []
        self.dfs(s, 0, "", res)
        return res

    def dfs(self, s, idx, path, res):
        # Backtrack
        if idx > 4:
            return

        # Select candidate when condition satisfied
        if idx == 4 and not s:
            res.append(path[:-1])
            return

        # Explore all potential candidates
        for i in range(1, len(s)+1):
            if s[:i]=='0' or (s[0]!='0' and 0 < int(s[:i]) < 256):
                self.dfs(s[i:], idx+1, path+s[:i]+".", res)
```

### Dynamic Programming

LeetCode Problems:
One dimension:
- [91. Decode Ways](https://leetcode.com/problems/decode-ways/)
- [70. Climing Stairs](https://leetcode.com/problems/climbing-stairs/)
- [509. Fibonacci Number](https://leetcode.com/problems/fibonacci-number/)
- [256. Paint House](https://leetcode.com/problems/paint-house/)

Two dimention:
- [62. Unique Paths](https://leetcode.com/problems/unique-paths/)
- [322. Coin Change](https://leetcode.com/problems/coin-change/)
- [518. Coin Change 2](https://leetcode.com/problems/coin-change-2/)
- [416. Partition Equal Subset Sum](https://leetcode.com/problems/partition-equal-subset-sum/)

### Monotone Stack

LeetCode Problems:
- [654. Maximum Binary Tree](https://leetcode.com/problems/maximum-binary-tree/)
- [901. ]
- [503. ]
- [496. ]
- [739. ]
- [856. ]
- [907. ]
- [89. ]
- [828. ]
- [84. ]
- [85. ]
- [42. ]


### Tree Traversal

Iterative preorder:
- [144. Binary Tree Preorder Traversal](https://leetcode.com/problems/binary-tree-preorder-traversal/)
```py
class Solution:
    def preorderTraversal(self, root: TreeNode) -> List[int]:
        stack = []
        res = []

        while stack or root:
            if root:
                res.append(root.val)
                stack.append(root)
                root = root.left
            else:
                tmpNode = stack.pop()
                root = tmpNode.right

        return res
```

Iterative inorder:
- [94. Binary Tree Inorder Traversal](https://leetcode.com/problems/binary-tree-inorder-traversal/)
```py
class Solution:
    def inorderTraversal(self, root: TreeNode) -> List[int]:
        stack = []
        res = []

        while stack or root:
            if root:
                stack.append(root)
                root = root.left
            else:
                tmpNode = stack.pop()
                res.append(tmpNode.val)
                root = tmpNode.right

        return res
```

Iterative postorder:
- [145. Binary Tree Postorder Traversal](https://leetcode.com/problems/binary-tree-postorder-traversal/)
```py
class Solution:
    def postorderTraversal(self, root: TreeNode) -> List[int]:
        res = []
        stack = []
        last = None

        while stack or root:
            if root:
                stack.append(root)
                root = root.left
            else:
                tmpNode = stack[-1]
                if tmpNode.right and tmpNode.right != last:
                    root = tmpNode.right
                else:
                    res.append(tmpNode.val)
                    last = stack.pop()

        return res
```

BFS
- [102. Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/)
- [199. Binary Tree Right Side View](https://leetcode.com/problems/binary-tree-right-side-view/)
```py
level = [root]
res = []
while level:
    res.append([node.val for node in level])
    level = [child for node in level for child in [node.left, node.right] if child]
return res
```

### Union Find
- [684. Redundant Connection](https://leetcode.com/problems/redundant-connection/)
- [305. Number of Islands II](https://leetcode.com/problems/number-of-islands-ii/)
```py
parent = [0] * N
def find(x):
    if parent[x] == 0:
        return x
    parent[x] = find(parent[x])
    return parent[x]

def union(x, y):
    parent_x = find(x)
    parent_y = find(y)
    if parent_x == parent_y:
        return False
    parent[parent_x] = parent_y
    return True
```


### Binary search
- [528. Random Pick with Weight](https://leetcode.com/problems/random-pick-with-weight/)
Two ways to do binary search.

[l, h) - like bisect
```py
l, h = 0, len(a)

while l < h:
    m = (l + h) // 2

    if :
        l = m + 1
    else:
        h = m

return l
```

[l, h]
```py
l, h = 0, len(a)-1

while l <= h:
    m = (l + h) // 2

    if :
        return
    elif:
        l = m + 1
    else:
        h = m - 1

return -1
```

### Substring and Subsequence

Subsequence:
- [516. Longest Palindromic Subsequence](https://leetcode.com/problems/longest-palindromic-subsequence/)
- [1143. Longest Common Subsequence](https://leetcode.com/problems/longest-common-subsequence/)

Substring:
- [5. Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/)
- [647. Palindromic Substrings](https://leetcode.com/problems/palindromic-substrings/)
