# LeetCode-Longest-Consecutive-Sequence

## Solution
```cs
public class Solution {
    public int LongestConsecutive(int[] nums) {
        int max = 0;
        int count, next;
        var set = new HashSet<int>(nums);
        
        foreach (var num in set) {
            if (!(set.Contains(num-1))) {
                count = 1;
                next = num + 1;
                while (set.Contains(next)) {
                    count += 1;
                    next += 1;
                }
                
                max = Math.Max(count, max);
            }
        }
        
        return max;
    }
}
```
