# Leetcode
Doing leetcode problems for preparing interview.

## Day 1 (5/24/2020) Double Pointer
### #167 Two Sum II (Easy https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)
```python
##python solution
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

##python solution
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        d = {nums[0]:0}                 //create a dict and put the 0 index in the dict
        for i in range(1, len(nums)):   //loop for the nums length
            rem = target - nums[i]      //get the rem and find it in the dict
            if rem in d:
                return d[rem], i      //return the current rem index and current index
            else:
                d[nums[i]] = i     //store the current index and its item into dict
         
        
        
        //dict -- "nums item" : "nums index"
```

```java
##java solution
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
```python
##python solution
class Solution:
    def judgeSquareSum(self, c: int) -> bool:
        a = 0
        while(a*a<=c):
            if sqrt(c-a*a) == int(sqrt(c-a*a)):
                return True
            else: a+=1
        return False
```

```java
##java solution
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
### #88 Merge Sorted Array (Easy https://leetcode.com/problems/merge-sorted-array/)
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

## Day 5 (12/25/2020) 
### #141 Assign Cookies (Easy https://leetcode.com/problems/third-maximum-number/)
```python
class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        try:
            slow = head
            fast = head.next
            while slow is not fast:
                slow = slow.next
                fast = fast.next.next
            return True
        except:
            return False
```

### #524 Longest Word in Dictionary through Deleting (Medium https://leetcode.com/problems/longest-word-in-dictionary-through-deleting/)
```python
class Solution:
    def findLongestWord(self, s:str, d:List[str]) -> str:
        d.sort(key = lambda x: (-len(x), x))
        for word in d:
            i = 0
            for c in s:
                if i < len(word) & c == word[i]:
                    i += 1
            if i == len(word):
                return word
        return ""       
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



                



