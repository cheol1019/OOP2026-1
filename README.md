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

package homework;

public class homework3 {
    public static void main(String[] args) {
        long[] fibo = new long[22];

        fibo[1] = 1;
        fibo[2] = 1;

        for (int i = 3; i <= 21; i++) {
            fibo[i] = fibo[i - 1] + fibo[i - 2];
        }

        for (int i = 1; i <= 20; i++) {
            double ratio = (double) fibo[i + 1] / fibo[i];
            System.out.printf("%d/%d = %.6f%n", fibo[i + 1], fibo[i], ratio);
        }
    }
} ![Alt homework11](./images/homework3.png)

package homework;

public class homework4 {
    public static void main(String[] args) {
        int i, j;

        for (j = 1; j <= 9; j++) {
            for (i = 1; i <= 9; i++) {
                System.out.printf("%d*%d=%-2d\t", i, j, i * j);
            }
            System.out.println();
        }
    }
} ![Alt homework11](./images/homework4.png)

package homework;

public class homework5 {
    public static void main(String[] args) {
        int terms = 20;

        // 1. Gregory-Leibniz Series
        double leibnizSum = 0.0;
        System.out.println("=== 1. Gregory-Leibniz Series (최초 20항) ===");
        for (int k = 0; k < terms; k++) {
            double term = Math.pow(-1, k) / (2 * k + 1);
            leibnizSum += term;
            double currentPi = 4.0 * leibnizSum;
            System.out.printf("k = %2d: PI ≈ %.10f%n", k + 1, currentPi);
        }

        System.out.println();

        // 2. Madhava Series
        double madhavaSum = 0.0;
        double sqrt12 = Math.sqrt(12);
        System.out.println("=== 2. Madhava Series (최초 20항) ===");
        for (int k = 0; k < terms; k++) {
            double term = Math.pow(-1, k) / ((2 * k + 1) * Math.pow(3, k));
            madhavaSum += term;
            double currentPi = sqrt12 * madhavaSum;
            System.out.printf("k = %2d: PI ≈ %.10f%n", k + 1, currentPi);
        }

        System.out.println();
        System.out.printf("실제 Math.PI 값: %.10f%n", Math.PI);
    }
} ![Alt homework11](./images/homework5.png)
