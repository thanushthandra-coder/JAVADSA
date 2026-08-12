1) Merge Sorted Array

program:
import java.util.Arrays;

public class Main {

    public static void merge(int[] nums1, int m, int[] nums2, int n) {
        int i = m - 1;
        int j = n - 1;
        int k = m + n - 1;

        while (i >= 0 && j >= 0) {
            if (nums1[i] > nums2[j]) {
                nums1[k] = nums1[i];
                i--;
            } else {
                nums1[k] = nums2[j];
                j--;
            }
            k--;
        }

        while (j >= 0) {
            nums1[k] = nums2[j];
            j--;
            k--;
        }
    }

    public static void main(String[] args) {

        int[] nums1 = {1, 2, 3, 0, 0, 0};
        int m = 3;

        int[] nums2 = {2, 5, 6};
        int n = 3;

        merge(nums1, m, nums2, n);

        System.out.println(Arrays.toString(nums1));
    }
}

output:

[1, 2, 2, 3, 5, 6]

2) Majority Element

program:
public class Main {
    public static void main(String[] args) {
        int[] nums = {2, 2, 1, 1, 1, 2, 2};

        int candidate = nums[0];
        int count = 0;

        for (int num : nums) {
            if (count == 0) {
                candidate = num;
            }

            if (num == candidate) {
                count++;
            } else {
                count--;
            }
        }

        System.out.println(candidate);
    }
}

output:

2

3) Contains Duplicate

program:
import java.util.HashSet;

public class Main {
    public static void main(String[] args) {
        int[] nums = {1, 2, 3, 1};

        HashSet<Integer> set = new HashSet<>();
        boolean duplicate = false;

        for (int num : nums) {
            if (set.contains(num)) {
                duplicate = true;
                break;
            }

            set.add(num);
        }

        System.out.println(duplicate);
    }
}

output:

true

4) Missing Number

public class Main {
    public static void main(String[] args) {
        int[] nums = {3, 0, 1};

        int n = nums.length;
        int sum = n * (n + 1) / 2;

        for (int num : nums) {
            sum -= num;
        }

        System.out.println(sum);
    }
}

output:

2

5) Intersection of Two Arrays

program:
import java.util.HashSet;

public class Main {
    public static void main(String[] args) {
        int[] nums1 = {1, 2, 2, 1};
        int[] nums2 = {2, 2};

        HashSet<Integer> set1 = new HashSet<>();
        HashSet<Integer> result = new HashSet<>();

        for (int num : nums1) {
            set1.add(num);
        }

        for (int num : nums2) {
            if (set1.contains(num)) {
                result.add(num);
            }
        }

        System.out.println(result);
    }
}

output:

[2]

6) Intersection of Two Arrays II

program:
import java.util.HashMap;
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        int[] nums1 = {1, 2, 2, 1};
        int[] nums2 = {2, 2};

        HashMap<Integer, Integer> map = new HashMap<>();
        ArrayList<Integer> result = new ArrayList<>();

        for (int num : nums1) {
            map.put(num, map.getOrDefault(num, 0) + 1);
        }

        for (int num : nums2) {
            if (map.getOrDefault(num, 0) > 0) {
                result.add(num);
                map.put(num, map.get(num) - 1);
            }
        }

        System.out.println(result);
    }
}

output:

[2, 2]

7) Third Maximum Number

program:
public class Main {
    public static void main(String[] args) {
        int[] nums = {3, 2, 1};

        Long first = null;
        Long second = null;
        Long third = null;

        for (int num : nums) {
            long n = num;

            if ((first != null && n == first) ||
                (second != null && n == second) ||
                (third != null && n == third)) {
                continue;
            }

            if (first == null || n > first) {
                third = second;
                second = first;
                first = n;
            } else if (second == null || n > second) {
                third = second;
                second = n;
            } else if (third == null || n > third) {
                third = n;
            }
        }

        if (third == null) {
            System.out.println(first);
        } else {
            System.out.println(third);
        }
    }
}

output:

1

8) Assign Cookies

program:
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] g = {1, 2, 3};
        int[] s = {1, 1};

        Arrays.sort(g);
        Arrays.sort(s);

        int child = 0;
        int cookie = 0;

        while (child < g.length && cookie < s.length) {
            if (s[cookie] >= g[child]) {
                child++;
            }

            cookie++;
        }

        System.out.println(child);
    }
}

output:

1

9) Array Partition I

program:
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] nums = {1, 4, 3, 2};

        Arrays.sort(nums);

        int sum = 0;

        for (int i = 0; i < nums.length; i += 2) {
            sum += nums[i];
        }

        System.out.println(sum);
    }
}

output:

4

10) Maximum Product of Three Numbers

program:
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {

        int[] nums = {1, 2, 3, 4};

        Arrays.sort(nums);

        int n = nums.length;

        // Maximum product can be:
        // 1. Three largest numbers
        // 2. Two smallest numbers and the largest number
        int product1 = nums[n - 1] * nums[n - 2] * nums[n - 3];
        int product2 = nums[0] * nums[1] * nums[n - 1];

        int result = Math.max(product1, product2);

        System.out.println("Maximum Product: " + result);
    }
}

output:

Maximum Product: 24

11) 
