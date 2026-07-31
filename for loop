1. Print all elements of an array.

public class PrintArray {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};

        for (int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }
    }
}

output

10
20
30
40
50

2. 

public class SumArray {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};
        int sum = 0;

        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];
        }

        System.out.println("Sum = " + sum);
    }
}

output:

Sum = 150


3.

public class AverageArray {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};
        int sum = 0;

        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];
        }

        double average = (double) sum / arr.length;
        System.out.println("Average = " + average);
    }
}

output:

Average = 30.0

4.Find the largest element.

import java.util.Arrays;

public class LargestElement {
    public static void main(String[] args) {
        int[] arr = {10, 25, 7, 40, 18};

        int largest = Arrays.stream(arr).max().getAsInt();

        System.out.println("Largest = " + largest);
    }
}

output:

Largest = 40

5.Find the smallest element.

import java.util.Arrays;

public class SmallestElement {
    public static void main(String[] args) {
        int[] arr = {10, 25, 7, 40, 18};

        int smallest = Arrays.stream(arr).min().getAsInt();

        System.out.println("Smallest = " + smallest);
    }
}

output:

Smallest = 7

6. Count even and odd numbers.

import java.util.Arrays;

public class EvenOddCount {
    public static void main(String[] args) {
        int[] arr = {10, 25, 7, 40, 18};

        long even = Arrays.stream(arr)
                          .filter(n -> n % 2 == 0)
                          .count();

        long odd = arr.length - even;

        System.out.println("Even Count = " + even);
        System.out.println("Odd Count = " + odd);
    }
}

output:

Even Count = 3
Odd Count = 2


7. Reverse an array.

public class ReverseArray {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};

        for (int i = arr.length - 1; i >= 0; i--) {
            System.out.print(arr[i] + " ");
        }
    }
}

output:

50 40 30 20 10 


8.Search for a given element.

import java.util.Arrays;

public class SearchElement {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};
        int key = 30;

        boolean found = Arrays.stream(arr).anyMatch(n -> n == key);

        System.out.println(found);
    }
}

output:

true

9. Count the occurrence of a specific number.

import java.util.Arrays;

public class CountOccurrence {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 20, 40, 20, 50};
        int key = 20;

        long count = Arrays.stream(arr)
                           .filter(n -> n == key)
                           .count();

        System.out.println("Occurrences = " + count);
    }
}

output:

Occurrences = 3

10. Find the second largest element.

import java.util.Arrays;

public class SecondLargest {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};

        int secondLargest = Arrays.stream(arr)
                                  .distinct()
                                  .boxed()
                                  .sorted((a, b) -> b - a)
                                  .skip(1)
                                  .findFirst()
                                  .get();

        System.out.println("Second Largest = " + secondLargest);
    }
}

output:

Second Largest = 40

11.Remove duplicate elements.

import java.util.Arrays;

public class RemoveDuplicates {
    public static void main(String[] args) {
        int[] arr = {1, 2, 2, 3, 4, 4, 5};

        Arrays.stream(arr)
              .distinct()
              .forEach(n -> System.out.print(n + " "));
    }
}

output:

1 2 3 4 5 

12. Merge two arrays.

import java.util.Arrays;

public class MergeArrays {
    public static void main(String[] args) {
        int[] arr1 = {10, 20, 30};
        int[] arr2 = {40, 50, 60};

        int[] merged = Arrays.copyOf(arr1, arr1.length + arr2.length);
        System.arraycopy(arr2, 0, merged, arr1.length, arr2.length);

        System.out.println(Arrays.toString(merged));
    }
}

output:

[10, 20, 30, 40, 50, 60]


13. Find the missing number (1 to N).

public class MissingNumber {
    public static void main(String[] args) {
        int[] arr = {1, 2, 4, 5};
        int n = 5;

        int total = n * (n + 1) / 2;
        int sum = 0;

        for (int num : arr) {
            sum += num;
        }

        System.out.println("Missing Number = " + (total - sum));
    }
}

output:

Missing Number = 3

14. Move all zeros to the end.

import java.util.Arrays;

public class MoveZeros {
    public static void main(String[] args) {
        int[] arr = {1, 0, 2, 0, 3, 4, 0, 5};

        int[] result = Arrays.stream(arr)
                             .filter(x -> x != 0)
                             .toArray();

        int[] output = Arrays.copyOf(result, arr.length);

        System.out.println(Arrays.toString(output));
    }
}

output:

[1, 2, 3, 4, 5, 0, 0, 0]


15.Rotate array left by one position.

import java.util.Arrays;

public class LeftRotate {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};

        int first = arr[0];
        System.arraycopy(arr, 1, arr, 0, arr.length - 1);
        arr[arr.length - 1] = first;

        System.out.println(Arrays.toString(arr));
    }
}

output:

[20, 30, 40, 50, 10]


16.Rotate array right by one position.

import java.util.Arrays;

public class RightRotate {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};

        int last = arr[arr.length - 1];

        System.arraycopy(arr, 0, arr, 1, arr.length - 1);

        arr[0] = last;

        System.out.println(Arrays.toString(arr));
    }
}


output:

[50, 10, 20, 30, 40]

17.Find the frequency of each element.

import java.util.HashMap;

public class FrequencyOfElements {
    public static void main(String[] args) {
        int[] arr = {10, 20, 10, 30, 20, 10, 40};

        HashMap<Integer, Integer> map = new HashMap<>();

        for (int num : arr) {
            map.put(num, map.getOrDefault(num, 0) + 1);
        }

        System.out.println("Frequency of each element:");
        map.forEach((key, value) -> System.out.println(key + " = " + value));
    }
}

output:

Frequency of each element:
20 = 2
40 = 1
10 = 3
30 = 1

18. Sort an array in ascending order (without using Arrays.sort()).

public class AscendingSort {
    public static void main(String[] args) {
        int[] arr = {50, 20, 40, 10, 30};

        for (int i = 0; i < arr.length - 1; i++) {
            for (int j = 0; j < arr.length - 1 - i; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }

        System.out.println("Sorted Array:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}

output:

Sorted Array:
10 20 30 40 50 

19. Sort an array in descending order.

import java.util.Arrays;
import java.util.Collections;

public class DescendingSort {
    public static void main(String[] args) {
        Integer[] arr = {50, 20, 40, 10, 30};

        Arrays.sort(arr, Collections.reverseOrder());

        System.out.println("Descending Order:");
        for (int n : arr) {
            System.out.print(n + " ");
        }
    }
}

output:

Descending Order:
50 40 30 20 10

20.  Find the intersection of two arrays

import java.util.Arrays;

public class ArrayIntersection {
    public static void main(String[] args) {
        int[] arr1 = {1, 2, 3, 4, 5};
        int[] arr2 = {3, 4, 5, 6, 7};

        int[] intersection = Arrays.stream(arr1)
                .filter(x -> Arrays.stream(arr2).anyMatch(y -> y == x))
                .toArray();

        System.out.println("Intersection:");
        for (int n : intersection) {
            System.out.print(n + " ");
        }
    }
}

output:

Intersection:
3 4 5 

21. Find the union of two arrays.

public class UnionArray {
    public static void main(String[] args) {
        int[] a = {1, 2, 3};
        int[] b = {3, 4, 5};

        int[] union = new int[a.length + b.length];

        System.arraycopy(a, 0, union, 0, a.length);
        System.arraycopy(b, 0, union, a.length, b.length);

        for (int i = 0; i < union.length; i++) {
            System.out.print(union[i] + " ");
        }
    }
}

output:

1 2 3 3 4 5

22. Find all pairs whose sum equals a target value.

public class PairSum {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        int target = 5;

        for (int i = 0; i < arr.length; i++) {
            for (int j = i + 1; j < arr.length; j++) {
                if (arr[i] + arr[j] == target) {
                    System.out.println(arr[i] + " " + arr[j]);
                }
            }
        }
    }
}

output:

1 4
2 3

23.Find the maximum subarray sum (Kadane's Algorithm).

public class KadaneAlgorithm {
    public static void main(String[] args) {
        int[] arr = {-2, 1, -3, 4, -1, 2, 1, -5, 4};

        int currentSum = arr[0];
        int maxSum = arr[0];

        for (int i = 1; i < arr.length; i++) {
            currentSum = Math.max(arr[i], currentSum + arr[i]);
            maxSum = Math.max(maxSum, currentSum);
        }

        System.out.println("Maximum Subarray Sum = " + maxSum);
    }
}

output:

Maximum Subarray Sum = 6

24.Find leaders in an array.

public class LeadersInArray {
    public static void main(String[] args) {
        int[] arr = {16, 17, 4, 3, 5, 2};

        int maxFromRight = arr[arr.length - 1];
        System.out.print(maxFromRight + " ");

        for (int i = arr.length - 2; i >= 0; i--) {
            if (arr[i] >= maxFromRight) {
                maxFromRight = arr[i];
                System.out.print(maxFromRight + " ");
            }
        }
    }
}


output:

2 5 17 

25.Find the equilibrium index.

public class EquilibriumIndex {
    public static void main(String[] args) {
        int[] arr = {1, 3, 5, 2, 2};

        int totalSum = 0;
        int leftSum = 0;

        // Calculate total sum
        for (int i = 0; i < arr.length; i++) {
            totalSum += arr[i];
        }

        // Find equilibrium index
        for (int i = 0; i < arr.length; i++) {
            totalSum -= arr[i];

            if (leftSum == totalSum) {
                System.out.println("Equilibrium Index: " + i);
                return;
            }

            leftSum += arr[i];
        }

        System.out.println("No Equilibrium Index");
    }
}

output:

Equilibrium Index: 2
