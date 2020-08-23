# Leetcode
Doing leetcode problems for preparing interview.

## Day 1 (5/24/2020) Double Pointer
### #167 Two Sum II (Easy https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)
```##python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        i = 0
        j = len(numbers)-1
        while (i < j):
            if numbers[i] + numbers[j] == target:
                return [i+1, j+1]
            elif numbers[i] + numbers[j] < target:
                i+=1
            else: j-=1
        return [ ]
```

```##java
class Solution {
    public int[] twoSum(int[] numbers, int target) {
        if(numbers == null) return null;
        int i = 0, j = numbers.length - 1;
        while(i<j){
            int sum = numbers[i] + numbers[j];
            if(sum == target){
                return new int[]{i+1,j+1};
            }else if(sum < target){
                i++;
            }else if(sum > target){
                j--;
            }
        }
         return null;
    } 
}
```

### #633 Sum of Square Numbers (Easy https://leetcode.com/problems/sum-of-square-numbers/)
```##python
class Solution:
    def judgeSquareSum(self, c: int) -> bool:
        a = 0
        while(a*a<=c):
            if sqrt(c-a*a) == int(sqrt(c-a*a)):
                return True
            else: a+=1
        return False
```

```##java
class Solution {
     public boolean judgeSquareSum(int target) {
         if (target < 0) return false;
         int i = 0, j = (int) Math.sqrt(target);
         while (i <= j) {
             int powSum = i * i + j * j;
             if (powSum == target) {
                 return true;
             } else if (powSum > target) {
                 j--;
             } else {
                 i++;
             }
         }
     return false;
     }
}
```

## Day 2 (5/28/2020)
### #345 Reverse Vowels of a String (Easy https://leetcode.com/problems/reverse-vowels-of-a-string/)
```python
class Solution:
    def reverseVowels(self, s: str) -> str:
        string = list(s)
        l = 0
        r = len(s) - 1
        vowels = 'aeiou'
        
        while l < r:
            if string[l].lower() not in vowels:
                l += 1
            elif string[r].lower() not in vowels:
                r -=1
            else:
                string[l], string[r] = string[r], string[l]
                l += 1
                r -=1
        return ''.join(string)
```


## Day 3 (5/30/2020)
### #88 Merge Sorted Array (Easy https://leetcode.com/problems/reverse-vowels-of-a-string/)
```python
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        while m > 0 and n > 0:
            if nums2[n-1] > nums1[m-1]:
                nums1[m-1+n] = nums2[n-1]
                n -= 1
            else: 
                nums1[m-1], nums1[m-1+n] = nums1[m-1+n], nums1[m-1]
                m -= 1
        if m == 0 and n > 0 :
            nums1[:n] = nums2[:n]
```

### #680 Valid Palindrome II (Easy https://leetcode.com/problems/valid-palindrome-ii/)
```python
class Solution:
    def validPalindrome(self, s: str) -> bool:
        l = 0
        r = len(s)-1
        while l < r:
            if s[l] == s[r]:
                l += 1
                r -= 1
            else:
                return s[l:r] == s[l:r][::-1] or s[l+1:r+1] == s[l+1:r+1][::-1]
        return True
```

## Day 4 (6/24/2020) Greedy Thinking
### #455 Assign Cookies (Easy https://leetcode.com/problems/assign-cookies/)
```python
class Solution:
    def findContentChildren(self, g: List[int], s: List[int]) -> int:
        g.sort()
        s.sort()
        child  = 0 
        cookie = 0
        
        while child < len(g) and cookie < len(s):
            if g[child] <= s[cookie]:
                child += 1
            cookie += 1
        return child    
```



                



