# Two Sum

|  |  |
|  ---  | ---  |
| Difficulty  | Easy |
| Tags  | Array, Hash Table |
|  |  |

https://leetcode.com/problems/two-sum/

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.

Example 1:
```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Output: Because nums[0] + nums[1] == 9, we return [0, 1].
```

Example 2:
```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

Example 3:
```
Input: nums = [3,3], target = 6
Output: [0,1]
```

Constraints:
```
2 <= nums.length <= 103
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists.
```

---

Solution 1  
|  |  |
|  ---  | ---  |
| time complexity | O(n^2) |
| space complexity | O(1) |
|  |  |

``` java
    public static int[] twoSum(int[] nums, int target) {
		for(int i = 0; i < nums.length - 1; i++) {
			for(int j = i + 1; j < nums.length; j++) {
				if (nums[i] + nums[j] == target) {
					return new int[] {i, j};
				}
			}
		}
		return null;
	}
```

---

Solution 2  
|  |  |
|  ---  | ---  |
| time complexity | O(n) |
| space complexity | O(n) |
|  |  |

``` java
    public static int[] twoSum2(int[] nums, int target) {
		HashMap<Integer, Integer> map = new HashMap<>();
		for (int i = 0; i < nums.length; i++) {
			map.put(nums[i], i);
		}

		for (int i = 0; i < nums.length; i++) {
			int complement = target - nums[i];
			if (map.containsKey(complement) && map.get(complement) != i) {
				return new int[] {i, map.get(complement)};
			}
		}
		throw new IllegalArgumentException("no solution");
	}
```

---

Solution 3  
|  |  |
|  ---  | ---  |
| time complexity | O(n) |
| space complexity | O(n) |
|  |  |

``` java
    public static int[] twoSum3(int[] nums, int target) {
		HashMap<Integer, Integer> map = new HashMap<>();
		for (int i = 0; i < nums.length; i++) {
			if (map.containsKey(target - nums[i])) {
				return new int[] {map.get(target - nums[i]), i};
			}
			map.put(nums[i], i);
		}
		throw new IllegalArgumentException("no solution");
	}
```