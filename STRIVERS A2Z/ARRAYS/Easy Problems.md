
# 1. Largest Element in an Array #

> [!question]
> - Given an array **arr[].** The task is to find the **largest** element and return it. 

> [!check]
> [Largest Element in a Array ](https://www.geeksforgeeks.org/problems/largest-element-in-array4009/0?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=largest-element-in-array )

```java
class Solution {
    public static int largest(int[] arr) {
        int max = arr[0];
        for(int i = 0; i<arr.length;i++){
            if(arr[i] > max) max = arr[i];
        }
        return max;
    }
}
```
 
---
# 2. Second Largest#

> [!question]
> - Given an array of **positive** integers **arr[]**, return the **second largest** element from the array. 
> - If the second largest element doesn't exist then return **-1.**
> - **Note**: The second largest element should not be equal to the largest element .

> [!Check]
> [Second Largest](https://www.geeksforgeeks.org/problems/second-largest3735/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=second-largest)


```java

class Solution {
    public int getSecondLargest(int[] arr) {
        
        int max = Integer.MIN_VALUE;
        int max_2 = Integer.MIN_VALUE;
        for(int i : arr){
            if(i > max) {
                max_2 = max;
                max = i;
            }
            else if(i > max_2 && i != max)  max_2 = i;
        }
        return (max_2 == Integer.MIN_VALUE) ? -1 : max_2;
    }
}
```

---
# 3. Check if an array is sorted and rotated#

> [!question]
> - Given an array `nums`, return `true`  if the array was originally sorted in non-decreasing order, then rotated **some** number of positions (including zero). Otherwise, return `false`.
> - **Note:** An array `A` rotated by `x` positions results in an array `B` of the same length such that `B[i] == A[(i+x) % A.length]` for every valid index `i`.

> [!Check]
> - [Check if array is sorted and rotated](https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/)

```java

class Solution {
	
	public boolean check(int[] arr) {
		int count_break = 0, len = arr.length;
		
		for (int i = 0; i < len; i++) {	
			if (arr[i] > arr[(i + 1) % len])
				count_break++;
		}
		return count_break <= 1;
	}
}
```

---
# 4. Remove Duplicates from Sorted Array#

> [!question]
> - Given an integer array `nums` sorted in **non-decreasing order**, remove the duplicates [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm) such that each unique element appears only **once**.
> - The **relative order** of the elements should be kept the **same**. Then return _the number of unique elements in_ `nums`.
> - Consider the number of unique elements of `nums` to be `k`, to get accepted, you need to do the following things:
> - Change the array `nums` such that the first `k` elements of `nums` contain the unique elements in the order they were present in `nums` initially. The remaining elements of `nums` are not important as well as the size of `nums`.
> - **Note:** An array `A` rotated by `x` positions results in an array `B` of the same length such that `B[i] == A[(i+x) % A.length]` for every valid index `i`.

> [!Check]
> - [Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

```java

class Solution {
	 public int removeDuplicates(int[] arr) {
		int j = 0;
		for (int i = 1; i < arr.length; i++) {
			  if (arr[j] != arr[i]) {
				j++;
				arr[j] = arr[i];
			}
		}
		return j + 1;
	}
}
```

---
# 5. Rotate Array#

> [!question]
> - Given an integer array `nums`, rotate the array to the right by `k` steps, where `k` is non-negative.

> [!Check]
> - [Rotate Array](https://leetcode.com/problems/rotate-array/)

```java

class Solution {

    public void rv(int[] arr, int s, int e) {
        while (s <= e) {
            int temp = arr[s];
            arr[s] = arr[e];
            arr[e] = temp;
            s++;
            e--;
        }
    }
    
    public void rotate(int[] nums, int k) {
        int n = nums.length;
        k = k % n;
        
        rv(nums, 0, n - k - 1);   // Reverse the first part
        rv(nums, n - k, n - 1);   // Reverse the second part
        rv(nums, 0, n - 1);       // Reverse the whole array
    }
    
}

```

---
# 6. Move all Zeros to end#

> [!question]
> - Given an integer array `nums`, move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.
> - **Note** that you must do this in-place without making a copy of the array.

### Approach ###

We can optimize the approach using 2 pointers i.e. i and j. The pointer j will point to the first 0 in the array and i will point to the next index.

Assume, the given array is {1, 0, 2, 3, 2, 0, 0, 4, 5, 1}. Now, initially, we will place the 2-pointers like the following:

![](https://static.takeuforward.org/wp/uploads/2023/06/Screenshot-2023-06-26-162005.png)

The algorithm will be the following.

##### ***Algorithm:***  ######

1. First, using a loop, we will place the pointer j. If we don’t find any 0, we will not perform the following steps.
2. After that, we will point i to index j+1 and start moving the pointer using a loop.
3. While moving the pointer i, we will do the following:
    1. **If a[i] != 0 i.e. a[i] is a non-zero element:** We will swap a[i] and a[j]. Now, the current j is pointing to the non-zero element a[i]. So, we will shift the pointer j by 1 so that it can again point to the first zero.
4. Finally, our array will be set in the right manner.

**Dry run:** _Please refer_ [_video_](https://youtu.be/wvcQg43_V8U) _for a detailed dry run._

The first 2 steps are shown below:

![](https://static.takeuforward.org/wp/uploads/2023/06/Screenshot-2023-06-26-162339.png)

> [!Check]
> - [Move - Zeros](https://leetcode.com/problems/move-zeroes/)

```java
class Solution {
	
    public void moveZeroes(int[] arr) {
        int n = arr.length;
        int z = 0;
        
        if (n == 1) return;
        
        // Find the first zero
        for (int i = 0; i < n; i++) {
            if (arr[i] == 0) {
                z = i;
                break;
            }
        }
        
        // If first zero not found, array already has no zero at start
        if (z == 0 && arr[z] != 0) return;
        
        // Swap non-zero elements to the left
        for (int i = z + 1; i < n; i++) {
            if (arr[i] != 0) {
                int temp = arr[i];
                arr[i] = arr[z];
                arr[z] = temp;
                z++;
            }
        }
    }
}

```

---
# 7. Sorted Array Search (Linear Search)#

> [!question]
> - Given an array, **arr[]** sorted in ascending order and an integer **k**. Return true if k is present in the array, otherwise, false.

> [!Check]
> - [Sorted Array Search - Linear Search](https://www.geeksforgeeks.org/problems/who-will-win-1587115621/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=who-will-win)

```java

class Solution {
    static boolean searchInSorted(int[] arr, int k) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == k) {
                return true;
            }
        }
        return false;
    }
}

```

---
# 8. Union of 2 Sorted with Duplicates#

> [!question]
> - Given two **sorted** arrays **a[]** and **b[]**, where each array may contain **duplicate** elements , the task is to return the elements in the **union** of the two arrays in **sorted** order.
> - Union of two arrays can be defined as the set containing distinct common elements that are present in either of the arrays.

> [!Check]
> - [Union of 2 Sorted Array](https://www.geeksforgeeks.org/problems/union-of-two-sorted-arrays-1587115621/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=union-of-two-sorted-arrays)

```java

class Solution {
    // Function to return a list containing the union of the two arrays.
    public static ArrayList<Integer> findUnion(int a[], int b[]) {
        int i = 0, j = 0;
        int n1 = a.length;
        int n2 = b.length;
        
        ArrayList<Integer> li = new ArrayList<>();
        
        while (i < n1 && j < n2) {
            if (a[i] <= b[j]) {
                if (li.size() == 0 || li.get(li.size() - 1) != a[i])
                    li.add(a[i]);
                i++;
            } else {
                if (li.size() == 0 || li.get(li.size() - 1) != b[j])
                    li.add(b[j]);
                j++;
            }
        }
        
        while (i < n1) {
            if (li.get(li.size() - 1) != a[i])
                li.add(a[i]);
            i++;
        }
        
        while (j < n2) {
            if (li.get(li.size() - 1) != b[j])
                li.add(b[j]);
            j++;
        }
        
        return li;
    }
}

```

---
# 9. Missing Number#

> [!question]
> - Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return _the only number in the range that is missing from the array._

> [!Check]
> - [Missing Number](https://leetcode.com/problems/missing-number/description/)

```java

class Solution {
    public int missingNumber(int[] nums) {
        int n = nums.length;
        int sum = 0;
        
        for (int i : nums) {
            sum += i;
        }

        int expectedSum = (n * (n + 1)) / 2;

        return expectedSum - sum;
    }
}

```

---
# 10. Single Number #

> [!question]
> - Given a **non-empty** array of integers `nums`, every element appears _twice_ except for one. Find that single one.
> - You must implement a solution with a linear runtime complexity and use only constant extra space.

### **Intuition:**

- Two important properties of XOR are the following:
	- XOR of two same numbers is always 0 i.e.` a ^ a = 0`. ←Property 1.  
	- XOR of a number with 0 will result in the number itself i.e.` 0 ^ a = a`.  ←Property 2

- Here all the numbers except the single number appear twice and so will form a pair. Now, if we perform XOR of all elements of the array, the XOR of each pair will result in 0 according to the XOR property 1.
- The result will be = 0 ^ (single number) = single number (according to property 2).

**_So, if we perform the XOR of all the numbers of the array elements, we will be left with a single number._**

> [!Check]
> - [ Single Number](https://leetcode.com/problems/single-number/)

```java

class Solution {
    public int singleNumber(int[] nums) {
        int xorr = 0;
        for (int i : nums) {
            xorr ^= i;
        }
        return xorr;
    }
}

```

---
# 11. Longest Subarray with sum K #

> [!question]
> - Given an array **`arr[]`** containing integers and an integer **`k`**, your task is to find the length of the longest subarray where the sum of its elements is equal to the given value **`k`**. If there is no subarray with sum equal to **`k`**, return **`0`**.

### **Intuition:**
- **Prefix Sum**:  
    Keep a running sum (prefix sum) as you go through the array.
    
- **Use a HashMap**:
    
    - Store prefix sums as keys and their **first occurrence index** as values.
        
    - This helps quickly check if there's a previous subarray with sum = `current_sum - k`.
        
- **Check for Valid Subarray**:
    
    - If `prefix_sum == k`, the subarray starts from index 0 to i → length = `i+1`.
        
    - If `prefix_sum - k` exists in the map, that means there's a subarray with sum = k → update the max length.
        
- **Don't Overwrite Map Values**:
    
    - Always keep the **first index** where a prefix sum appears to ensure the **longest** subarray is found.

> [!Check]
> - [ Longest Subarray Sum](https://www.geeksforgeeks.org/problems/longest-sub-array-with-sum-k0809/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=longest-sub-array-with-sum-k/)

```java



// User function Template for Java

class Solution {
    public int longestSubarray(int[] arr, int k) {
        int n = arr.length;
        Map<Integer,Integer> hash = new HashMap<>();
        int sum = 0,max = 0;
        for(int i = 0;i < n;i++){
            
            sum += arr[i];
            
            if(sum == k) max = Math.max(max,i+1);
            
            int rem = sum - k;
            
            if(hash.containsKey(rem)){
                int len = i - hash.get(rem);
                max = Math.max(max,len);
            }
            if(!hash.containsKey(sum)){
                hash.put(sum, i);    
            }
        }
        
        return max;
    }
}

```

---
