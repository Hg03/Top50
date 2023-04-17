**[Problem Statement](https://leetcode.com/problems/two-sum/)** -  Given an array of integers **arr** and an integer **k**, create a boolean function that checks if there exists two elements in **arr** such that we get **k** when we add them together.

> **Input** - arr = [4,5,1,7,2], k = 3

> **Output** - True

> **True** because we've found a pair i.e. 1,2 which sums upto 3

**Solution (Brute Force) -** 
1. Time Complexity - $O(n)^2$ 
2.  Space Complexity - $O(1)$

```python
# Iterating every pair one by one using nested for loops
def findPair(arr, k):
    for i in range(len(arr)):
        for j in range(i+1,len(arr)):
            if arr[i] + arr[j] == k:
                return True
    return False
```

**Solution (Using Two pointer at both ends) -**
1. Time Complexity - $O(nlogn)$
2. Space Complexity - Depends on the space complexity of particular sorting algorithm


```python
# We sort arr
# we create and initialize left to 0, and right to length - 1
# while left < right
  # if arr[left] + arr[right] < k, return true
  # else if arr[left] + arr[right] < k, increment left
  # else , we decrement right
  
def findPair(arr,k):
    arr.sort()
    left = 0
    right = len(arr) - 1
    while left < right:
        if arr[left] + arr[right] == k:
            return true
        elif arr[left] + arr[right] < k:
            left += 1
        else
            right -= 1
```

**Solution (Using Hashtable) -** 
1. Time Complexity - $O(1)$
2. Space Complexity - $O(1)$

```python
# Use hashtable i.e. dictionary
# iterate through elements and check if k - that element exist in hashtable or not, if exist return two elements
# else move forward
def findPair(arr, k):
    visisted = {}
    for element in arr:
        if visited.get(k-element):
            return True
        else:
            visited[element] = True
    return False
```
