```
R.1. Median of Array | Easy

To find the median of a list of integers, sort the list and find the middle element (or the average of the two middle elements for lists with an even length)

median: 中位数
determine: 确定
odd: 奇数
even: 偶数

# approach
# determine whether even: n%2 == 1
# odd length [1,4,2]: 2
# even length [1,4,2,3]: (2+3)/2 = 2.5

# pyton 3 / 2: 1.5
# pyton 3 // 2: 1
# Java 3 / 2: 1
# Java (double)  3 / 2: 1.5

# Python sorted_list = sorted(integer_list)
# Java int[] sortedList = Arrays.copyOf(integerList, n);
# Java Arrays.sort(sortedList);

# implementation

python:

class Solution:
    def median(self, integer_list):
        n = len(integer_list)
        if n == 0:
            return 0

        sorted_list = sorted(integer_list)
        if n % 2 == 1:
            median_value = sorted_list[n // 2]
        else:
            median_value = (sorted_list[n // 2 - 1] + sorted_list[n // 2]) / 2
        return median_value


# test case
nums1 = [1, 4, 2]
nums2 = [1, 4, 2, 3]
nums3 = []
nums4 = [0]

sol = Solution()
print(nums1)
print(sol.median(nums1))
print(nums2)
print(sol.median(nums2))
print(nums3)
print(sol.median(nums3))
print(nums4)
print(sol.median(nums4))


java:

import java.util.Arrays;

public class Solution {
    public double median(int[] integerList) {
        int n = integerList.length;
        if (n == 0) {
            return 0;
        }

        int[] sortedList = Arrays.copyOf(integerList, n);
        Arrays.sort(sortedList);

        if (n % 2 == 1) {
            return sortedList[n / 2];
        } else {
            return (double) (sortedList[n / 2 - 1] + sortedList[n / 2]) / 2;
        }
    }

    public static void main(String[] args) {
        Solution sol = new Solution();

        int[] nums1 = {1, 4, 2};
        int[] nums2 = {1, 4, 2, 3};
        int[] nums3 = {};
        int[] nums4 = {0};

        System.out.println(Arrays.toString(nums1));
        System.out.println(sol.median(nums1));
        System.out.println(Arrays.toString(nums2));
        System.out.println(sol.median(nums2));
        System.out.println(Arrays.toString(nums3));
        System.out.println(sol.median(nums3));
        System.out.println(Arrays.toString(nums4));
        System.out.println(sol.median(nums4));
    }
}
```