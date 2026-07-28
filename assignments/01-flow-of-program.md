1. Input a year and find whether it is a leap year or not.
import java.util.Scanner;

public class LeapYear {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a year: ");
        int year = sc.nextInt();

        if ((year % 400 == 0) || (year % 4 == 0 && year % 100 != 0)) {
            System.out.println(year + " is a Leap Year.");
        } else {
            System.out.println(year + " is Not a Leap Year.");
        }

        sc.close();
    }
}

output;

Enter a year: 2006
2006 is Not a Leap Year.


2. Take two numbers and print the sum of both.
import java.util.Scanner;

public class SumOfTwoNumbers {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter first number: ");
        int num1 = sc.nextInt();

        System.out.print("Enter second number: ");
        int num2 = sc.nextInt();

        int sum = num1 + num2;

        System.out.println("Sum = " + sum);

        sc.close();
    }
}

output;

Enter first number: 11
Enter second number: 22
Sum = 33

3. Take a number as input and print the multiplication table for it.

import java.util.Scanner;

public class MultiplicationTable {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number: ");
        int num = sc.nextInt();

        System.out.println("Multiplication Table of " + num + ":");

        for (int i = 1; i <= 10; i++) {
            System.out.println(num + " x " + i + " = " + (num * i));
        }

        sc.close();
    }
}

output;

Enter a number: 6
Multiplication Table of 6:
6 x 1 = 6
6 x 2 = 12
6 x 3 = 18
6 x 4 = 24
6 x 5 = 30
6 x 6 = 36
6 x 7 = 42
6 x 8 = 48
6 x 9 = 54
6 x 10 = 60

4. Take 2 numbers as inputs and find their HCF and LCM.
   
import java.util.Scanner;

public class HCFAndLCM {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter first number: ");
        int num1 = sc.nextInt();

        System.out.print("Enter second number: ");
        int num2 = sc.nextInt();

        int a = num1;
        int b = num2;

        // Find HCF (GCD) using Euclidean Algorithm
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }

        int hcf = a;
        int lcm = (num1 * num2) / hcf;

        System.out.println("HCF = " + hcf);
        System.out.println("LCM = " + lcm);

        sc.close();
    }
}

output;

Enter first number: 20
Enter second number: 15
HCF = 5
LCM = 60

5. Keep taking numbers as inputs till the user enters ‘x’, after that print sum of all.

import java.util.Scanner;

public class SumUntilX {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int sum = 0;

        while (true) {
            System.out.print("Enter a number (or 'x' to stop): ");
            String input = sc.next();

            if (input.equalsIgnoreCase("x")) {
                break;
            }

            sum += Integer.parseInt(input);
        }

        System.out.println("Sum = " + sum);

        sc.close();
    }
}

output;

Enter a number (or 'x' to stop): 12
Enter a number (or 'x' to stop): 17
Enter a number (or 'x' to stop): 13
Enter a number (or 'x' to stop): x
Sum = 42
