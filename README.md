# OOP2026
### Homework1
public class Homework1 {
    public static void main(String[] args) {
        int i, j;

        for (i = 0; i < 10; i++) {
            for (j = 0; j < 10; j++) {
                if (j <= i) {
                    System.out.print("#");
                } else {
                    System.out.print(" ");
                }
            }
            System.out.println("");
        }

        System.out.println();

        for (i = 0; i < 10; i++) {
            for (j = 0; j < 10; j++) {
                if (j < 10 - i) {
                    System.out.print("#");
                } else {
                    System.out.print(" ");
                }
            }
            System.out.println("");
        }

        System.out.println();

        for (i = 0; i < 10; i++) {
            for (j = 0; j < 10; j++) {
                if (j >= 9 - i) {
                    System.out.print("#");
                } else {
                    System.out.print(" ");
                }
            }
            System.out.println("");
        }

        System.out.println();

        for (i = 0; i < 10; i++) {
            for (j = 0; j < 10; j++) {
                if (j >= i) {
                    System.out.print("#");
                } else {
                    System.out.print(" ");
                }
            }
            System.out.println("");
        }
    }
}![Alt homework11](./images/homework1.png)


package homework;

public class homework2 {
    public static void main(String[] args) {
        int[] fibo = new int[20];

        fibo[0] = 1;
        fibo[1] = 1;

        for (int i = 2; i < 20; i++) {
            fibo[i] = fibo[i - 1] + fibo[i - 2];
        }

        for (int i = 0; i < 20; i++) {
            System.out.print(fibo[i] + " ");
        }
        System.out.println();
    }
}![Alt homework11](./images/homework2.png)
