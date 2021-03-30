### Backtracking

LeetCode Problems:
- [93. Restore IP Addresses](https://leetcode.com/problems/restore-ip-addresses/)
- [78. Subsets](https://leetcode.com/problems/subsets/)
- [90. Subsets II](https://leetcode.com/problems/subsets-ii/)
- [46. Permutations](https://leetcode.com/problems/permutations/)

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

Two dimention:
- [62. Unique Paths](https://leetcode.com/problems/unique-paths/)
