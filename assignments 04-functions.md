1. Define two methods to print the maximum and the minimum number respectively among three numbers entered by the user.

   import java.util.Scanner;

public class MaxMinMethods {

    static void maximum(int a, int b, int c) {
        int max = a;

        if (b > max)
            max = b;

        if (c > max)
            max = c;

        System.out.println("Maximum = " + max);
    }

    static void minimum(int a, int b, int c) {
        int min = a;

        if (b < min)
            min = b;

        if (c < min)
            min = c;

        System.out.println("Minimum = " + min);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter three numbers: ");
        int a = sc.nextInt();
        int b = sc.nextInt();
        int c = sc.nextInt();

        maximum(a, b, c);
        minimum(a, b, c);

        sc.close();
    }
}

output:

Enter three numbers: 12 33 32
Maximum = 33
Minimum = 12




