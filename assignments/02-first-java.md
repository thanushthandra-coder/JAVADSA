1. Write a program to print whether a number is even or odd, also take
input from the user

import java.util.Scanner;

public class EvenOdd {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number: ");
        int num = sc.nextInt();

        String[] result = {"Even", "Odd"};
        System.out.println(result[Math.abs(num % 2)]);

        sc.close();
    }
}

output:
Enter a number: 13
13 is Odd.


2. Take name as input and print a greeting message for that particular name.

import java.util.Scanner;

public class Greeting {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = sc.nextLine();

        System.out.println("Hello, " + name + "! Welcome.");

        sc.close();
    }
}

output:

Enter your name: Thanush
Hello, Thanush! Welcome!

=== Code Execution Successful ===

3. Write a program to input principal, time, and rate (P, T, R) from the user and
find Simple Interest.

import java.util.Scanner;

public class SimpleInterest {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Principal: ");
        double p = sc.nextDouble();

        System.out.print("Enter Time: ");
        double t = sc.nextDouble();

        System.out.print("Enter Rate: ");
        double r = sc.nextDouble();

        double si = (p * t * r) / 100;

        System.out.println("Simple Interest = " + si);

        sc.close();
    }
}


output:

Enter Principal (P): 1200
Enter Time (T) in years: 3
Enter Rate (R) in %: 5
Simple Interest = 180.0


4. Take in two numbers and an operator (+, -, *, /) and calculate the value. (Use if conditions)

import java.util.Scanner;

public class Calculator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter first number: ");
        double a = sc.nextDouble();

        System.out.print("Enter second number: ");
        double b = sc.nextDouble();

        System.out.print("Enter operator (+, -, *, /): ");
        char op = sc.next().charAt(0);

        switch (op) {
            case '+':
                System.out.println("Result = " + (a + b));
                break;
            case '-':
                System.out.println("Result = " + (a - b));
                break;
            case '*':
                System.out.println("Result = " + (a * b));
                break;
            case '/':
                System.out.println("Result = " + (a / b));
                break;
            default:
                System.out.println("Invalid operator");
        }

        sc.close();
    }
}

output:

Enter first number: 5
Enter second number: 3
Enter operator (+, -, *, /): *
Result = 15.0


5. Take 2 numbers as input and print the largest number.

import java.util.Scanner;

public class LargestNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter first number: ");
        int a = sc.nextInt();

        System.out.print("Enter second number: ");
        int b = sc.nextInt();

        System.out.println("Largest number = " + Math.max(a, b));

        sc.close();
    }
}

output:
Enter first number: 13
Enter second number: 2
Largest number = 13

6. Input currency in rupees and output in USD.

import java.util.Scanner;

public class CurrencyConverter {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter amount in Rupees (INR): ");
        double rupees = sc.nextDouble();

        // Example conversion rate: 1 USD = 87 INR
        double usd = rupees / 87.0;

        System.out.println("Amount in USD = $" + usd);

        sc.close();
    }
}

output:

Enter amount in Rupees (INR): 1320
Amount in USD = $15.172413793103448

7. To calculate Fibonacci Series up to n numbers.

import java.util.Scanner;

public class FibonacciSeries {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the number of terms: ");
        int n = sc.nextInt();

        int a = 0, b = 1, c;

        for (int i = 1; i <= n; i++) {
            System.out.print(a + " ");

            c = a + b;
            a = b;
            b = c;
        }

        sc.close();
    }
}

output:

Enter the number of terms: 51
0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597 2584 4181 6765 10946
17711 28657 46368 75025 121393 196418 317811 514229 832040 1346269 2178309
3524578 5702887 9227465 14930352 24157817 39088169 63245986 102334155 165580141
267914296 433494437 701408733 1134903170 1836311903 -1323752223 512559680 -811192543 -298632863 


8. To find out whether the given String is Palindrome or not.

import java.util.Scanner;

public class PalindromeString {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a String: ");
        String str = sc.nextLine();

        String reverse = "";

        for (int i = str.length() - 1; i >= 0; i--) {
            reverse = reverse + str.charAt(i);
        }

        System.out.println("Original String: " + str);
        System.out.println("Reversed String: " + reverse);
        System.out.println("Palindrome Check: " + str.equalsIgnoreCase(reverse));

        sc.close();
    }
}

output:

Enter a String: level
Original String: level
Reversed String: level
Palindrome Check: true

9. To find Armstrong Number between two given number. write a java code with out any conditions

10. import java.util.Scanner;

public class ArmstrongRange {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter starting number: ");
        int start = sc.nextInt();

        System.out.print("Enter ending number: ");
        int end = sc.nextInt();

        System.out.println("Armstrong Numbers:");

        for (int i = start; i <= end; i++) {

            int num = i;
            int sum = 0;
            int digits = String.valueOf(i).length();

            while (num > 0) {
                int rem = num % 10;
                sum += Math.pow(rem, digits);
                num /= 10;
            }

            String result = (sum == i) ? String.valueOf(i) : "";

            System.out.println(result);
        }

        sc.close();
    }
}


output:

Enter starting number: 2
Enter ending number: 100
Armstrong Numbers:
2
3
4
5
6
7
8
9
