# Remove Element

https://leetcode.com/problems/remove-element/

|  |  |
|  ---  | ---  |
| Difficulty  | Easy |
| Tags  | Array, Two Pointers |
|  |  |

---

Solution 1: two pointers  
|  |  |
|  ---  | ---  |
| time complexity | O(n) |
| space complexity | O(n) |
|  |  |

``` java
	public static int removeElement(int[] nums, int val) {
		int k = 0;

		for(int i = 0; i < nums.length; i++) {
			if(nums[i] != val){
				nums[k++] = nums[i];
			}
		}

		return k;
	}
```