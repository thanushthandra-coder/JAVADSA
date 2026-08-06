1) Build Array from Permutation.

program:
import java.util.Scanner;

public class BuildArrayFromPermutation {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        System.out.print("Enter the size of the array: ");
        int n = sc.nextInt();
        
        int[] nums = new int[n];
        int[] ans = new int[n];
        
        System.out.println("Enter the array elements:");
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }
        
        //Build the permutation array
        for (int i = 0; i < n; i++) {
            ans[i] = nums[nums[i]];
        }
        System.out.print("Output: ");
        for (int i = 0; i < n; i++) {
            System.out.print(ans[i] + " ");
        }
        sc.close();
    }
}

output:

Enter the size of the array: 6
Enter the array elements:
0 2 1 5 3 4

2) Concatenation of Array

program:
import java.util.Scanner;

public class ConcatenationOfArray {
    public static void main(String[] agrs) {
        Scanner sc = new Scanner(System.in);
        
        System.out.print("Enter the size of the array: ");
        int n = sc.nextInt();
        
        int[] nums = new int[n];
        int[] ans = new int[2 * n];
        
        System.out.println("Enter the array elements:");
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }
        
        // Concatenate the array with itself
        for (int i = 0; i < n; i++) {
            ans[i] = nums[i];
            ans[i + n] = nums[i];
        }
        System.out.print("Output: ");
        for (int i = 0; i < n; i++) {
            System.out.print(ans[i] + " ");
        }
        sc.close();
    }
}

output:

Enter the size of the array: 3
Enter the array elements:
1 2 1

3) Running Sum of 1d Array

program:
import java.util.Scanner;

public class RunningSumOf1DArray {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the size of the array: ");
        int n = sc.nextInt();

        int[] nums = new int[n];

        System.out.println("Enter the array elements:");
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        // Calculate running sum
        for (int i = 1; i < n; i++) {
            nums[i] = nums[i] + nums[i - 1];
        }

        System.out.print("Running Sum: ");
        for (int i = 0; i < n; i++) {
            System.out.print(nums[i] + " ");
        }

        sc.close();
    }
}

output:

Enter the size of the array: 4
Enter the array elements:
1 2 3 4

4) Richest Customer Wealth

program:
import java.util.Scanner;

public class RichestCustomerWealth {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of customers (rows): ");
        int m = sc.nextInt();

        System.out.print("Enter number of banks (columns): ");
        int n = sc.nextInt();

        int[][] accounts = new int[m][n];

        System.out.println("Enter the account balances:");
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                accounts[i][j] = sc.nextInt();
            }
        }

        int maxWealth = 0;

        // Find the richest customer
        for (int i = 0; i < m; i++) {
            int wealth = 0;

            for (int j = 0; j < n; j++) {
                wealth += accounts[i][j];
            }

            if (wealth > maxWealth) {
                maxWealth = wealth;
            }
        }

        System.out.println("Richest Customer Wealth: " + maxWealth);

        sc.close();
    }
}

output:

Enter number of customers (rows): 2
Enter number of banks (columns): 3
Enter the account balances:
1 2 3
3 2 1

5) Shuffle the Array

program:
import java.util.Scanner;

public class ShuffleTheArray {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the value of n: ");
        int n = sc.nextInt();

        int[] nums = new int[2 * n];
        int[] ans = new int[2 * n];

        System.out.println("Enter " + (2 * n) + " array elements:");
        for (int i = 0; i < 2 * n; i++) {
            nums[i] = sc.nextInt();
        }

        int index = 0;

        // Shuffle the array
        for (int i = 0; i < n; i++) {
            ans[index++] = nums[i];
            ans[index++] = nums[i + n];
        }

        System.out.print("Shuffled Array: ");
        for (int i = 0; i < 2 * n; i++) {
            System.out.print(ans[i] + " ");
        }

        sc.close();
    }
}

out put:
Enter the value of n: 3
Enter 6 array elements:
2 5 1 3 4 7

6) Kids With the Greatest Number of Candies

program:
import java.util.Scanner;

public class KidsWithGreatestCandies {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the number of kids: ");
        int n = sc.nextInt();

        int[] candies = new int[n];

        System.out.println("Enter the candies for each kid:");
        for (int i = 0; i < n; i++) {
            candies[i] = sc.nextInt();
        }

        System.out.print("Enter extra candies: ");
        int extraCandies = sc.nextInt();

        // Find the maximum candies
        int max = candies[0];
        for (int i = 1; i < n; i++) {
            if (candies[i] > max) {
                max = candies[i];
            }
        }

        System.out.print("Output: ");
        for (int i = 0; i < n; i++) {
            if (candies[i] + extraCandies >= max) {
                System.out.print("true ");
            } else {
                System.out.print("false ");
            }
        }

        sc.close();
    }
}

out put:

Enter the number of kids: 5
Enter the candies for each kid:
2 3 5 1 3
Enter extra candies: 3

Output: true true true false true

7) Number of Good Pairs

program:
import java.util.Scanner;

public class NumberOfGoodPairs {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the size of the array: ");
        int n = sc.nextInt();

        int[] nums = new int[n];

        System.out.println("Enter the array elements:");
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        int count = 0;

        // Count good pairs
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                if (nums[i] == nums[j]) {
                    count++;
                }
            }
        }

        System.out.println("Number of Good Pairs: " + count);

        sc.close();
    }
}

output:

Enter the size of the array: 6
Enter the array elements:
1 2 3 1 1 3

Number of Good Pairs: 4

8) How Many Numbers Are Smaller Than the Current Number.

program:
import java.util.Scanner;

public class SmallerNumbersThanCurrent {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the size of the array: ");
        int n = sc.nextInt();

        int[] nums = new int[n];
        int[] result = new int[n];

        System.out.println("Enter the array elements:");
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        // Count numbers smaller than each element
        for (int i = 0; i < n; i++) {
            int count = 0;
            for (int j = 0; j < n; j++) {
                if (nums[j] < nums[i]) {
                    count++;
                }
            }
            result[i] = count;
        }

        System.out.print("Output: ");
        for (int i = 0; i < n; i++) {
            System.out.print(result[i] + " ");
        }

        sc.close();
    }
}

output:

Input:
Enter the size of the array: 4
Enter the array elements:
6 5 4 8

Output: 2 1 0 3

9) Create Target Array in the Given Order

program:
import java.util.ArrayList;
import java.util.Scanner;

public class CreateTargetArrayInGivenOrder {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Input size
        System.out.print("Enter the size of the arrays: ");
        int n = sc.nextInt();

        int[] nums = new int[n];
        int[] index = new int[n];

        // Input nums array
        System.out.println("Enter the elements of nums:");
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        // Input index array
        System.out.println("Enter the elements of index:");
        for (int i = 0; i < n; i++) {
            index[i] = sc.nextInt();
        }

        // Create target array
        ArrayList<Integer> target = new ArrayList<>();

        for (int i = 0; i < n; i++) {
            target.add(index[i], nums[i]);
        }

        // Display target array
        System.out.print("Target Array: ");
        for (int value : target) {
            System.out.print(value + " ");
        }

        sc.close();
    }
}

input:
Enter the size of the arrays: 5
Enter the elements of nums:
0 1 2 3 4
Enter the elements of index:
0 1 2 2 1

output:
Target Array: 0 4 1 3 2


10) Check if the Sentence Is Pangram

 program:
 import java.util.Scanner;

public class CheckPangram {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the sentence: ");
        String sentence = sc.nextLine().toLowerCase();

        boolean[] letters = new boolean[26];

        // Mark each letter found
        for (int i = 0; i < sentence.length(); i++) {
            char ch = sentence.charAt(i);

            if (ch >= 'a' && ch <= 'z') {
                letters[ch - 'a'] = true;
            }
        }

        boolean isPangram = true;

        // Check if all letters are present
        for (int i = 0; i < 26; i++) {
            if (!letters[i]) {
                isPangram = false;
                break;
            }
        }

        System.out.println("Is Pangram: " + isPangram);

        sc.close();
    }
}

input:
Enter the sentence:
thequickbrownfoxjumpsoverthelazydog

output:
Is Pangram: true

11) Count Items Matching a Rule

program:
import java.util.*;

public class CountItemsMatchingRule {

    public static int countMatches(List<List<String>> items, String ruleKey, String ruleValue) {
        int index = 0;

        if (ruleKey.equals("type")) {
            index = 0;
        } else if (ruleKey.equals("color")) {
            index = 1;
        } else if (ruleKey.equals("name")) {
            index = 2;
        }

        int count = 0;

        for (List<String> item : items) {
            if (item.get(index).equals(ruleValue)) {
                count++;
            }
        }

        return count;
    }

    public static void main(String[] args) {
        List<List<String>> items = new ArrayList<>();

        items.add(Arrays.asList("phone", "blue", "pixel"));
        items.add(Arrays.asList("computer", "silver", "lenovo"));
        items.add(Arrays.asList("phone", "gold", "iphone"));

        String ruleKey = "color";
        String ruleValue = "silver";

        int result = countMatches(items, ruleKey, ruleValue);

        System.out.println("Matching items: " + result);
    }
}

output:

Matching items: 1

12) 
Matching items: 1

