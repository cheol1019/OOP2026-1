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

package homework;

public class homework6 {
    public static void main(String[] args) {
        int rows = 7; // 출력할 행의 수 (0차수부터 6차수까지 총 7개 행)
        int[][] binomial = new int[rows][];

        // 1. 가변 2차원 배열 생성 및 이항계수 계산
        for (int n = 0; n < rows; n++) {
            binomial[n] = new int[n + 1];

            for (int k = 0; k <= n; k++) {
                if (k == 0 || k == n) {
                    binomial[n][k] = 1;
                } else {
                    binomial[n][k] = binomial[n - 1][k - 1] + binomial[n - 1][k];
                }
            }
        }

        // 2. 파스칼의 삼각형 계수 형태 출력
        System.out.println("=== 이항계수 (파스칼의 삼각형) ===");
        for (int n = 0; n < rows; n++) {
            for (int k = 0; k <= n; k++) {
                System.out.print(binomial[n][k] + " ");
            }
            System.out.println();
        }

        System.out.println();

        // 3. 다항식 전개식 형태 출력 (차수 2부터 6까지 예시)
        System.out.println("=== (a+b)^n 전개식 표현 ===");
        for (int n = 2; n < rows; n++) {
            System.out.print("(a+b)^" + n + " = ");
            for (int k = 0; k <= n; k++) {
                int coeff = binomial[n][k];
                int aPow = n - k;
                int bPow = k;

                // 계수 출력 (1일 때는 생략, 단 상수항만 남는 경우는 제외)
                if (coeff > 1) {
                    System.out.print(coeff);
                }

                // a의 차수 출력
                if (aPow > 1) {
                    System.out.print("a^" + aPow);
                } else if (aPow == 1) {
                    System.out.print("a");
                }

                // b의 차수 출력
                if (bPow > 1) {
                    System.out.print("b^" + bPow);
                } else if (bPow == 1) {
                    System.out.print("b");
                }

                if (k < n) {
                    System.out.print(" + ");
                }
            }
            System.out.println();
        }
    }
} ![Alt homework11](./images/homework6.png)

package homework;

public class homework7 {
    public static void main(String[] args) {
        int data[] = new int[20];

        for (int i = 0; i < 20; i++) {
            data[i] = (int) (Math.random() * 100);
        }

        System.out.println("=== 정렬 전 (Original) ===");
        for (int i = 0; i < 20; i++) {
            System.out.print(data[i] + " ");
        }
        System.out.println("\n");

        for (int i = 0; i < 20 - 1; i++) {
            int minIndex = i; 

            for (int j = i + 1; j < 20; j++) {
                if (data[j] < data[minIndex]) {
                    minIndex = j; 
                }
            }

            int temp = data[i];
            data[i] = data[minIndex];
            data[minIndex] = temp;
        }

        System.out.println("=== 선택 정렬 후 (Sorted) ===");
        for (int i = 0; i < 20; i++) {
            System.out.print(data[i] + " ");
        }
        System.out.println();
    }
} ![Alt homework11](./images/homework7.png)

package homework;

public class homework8 {
    public static void main(String[] args) {
        int students = 30;
        int subjects = 4;

        int[][] score = new int[students][subjects + 1];

        for (int i = 0; i < students; i++) {
            int sum = 0;
            for (int j = 0; j < subjects; j++) {
                score[i][j] = (int) (Math.random() * 101);
                sum += score[i][j];
            }
            score[i][subjects] = sum;
        }

        System.out.printf("%-4s\t%-4s\t%-4s\t%-4s\t%-4s\t%-4s\t%-6s%n", 
                          "번호", "국어", "영어", "수학", "과학", "총점", "평균");
        System.out.println("---------------------------------------------------------");

        for (int i = 0; i < students; i++) {
            int studentNum = i + 1;
            int kor = score[i][0];
            int eng = score[i][1];
            int math = score[i][2];
            int sci = score[i][3];
            int sum = score[i][4];
            double avg = (double) sum / subjects;

            System.out.printf("%-4d\t%-4d\t%-4d\t%-4d\t%-4d\t%-4d\t%-6.2f%n",
                              studentNum, kor, eng, math, sci, sum, avg);
        }
    }
} ![Alt homework11](./images/homework8.png)

package homework;

public class homework10 {
    public static void main(String[] args) {
        int array_count, max_value, bin_size, display_scale, hist_size;

        if (args.length == 4) {
            array_count = Integer.parseInt(args[0]);
            max_value = Integer.parseInt(args[1]);
            bin_size = Integer.parseInt(args[2]);
            display_scale = Integer.parseInt(args[3]);
        } else {
            // 인자를 넣지 않고 그냥 실행했을 때 사용할 기본값
            array_count = 100;
            max_value = 100;
            bin_size = 10;
            display_scale = 1;
        }

        hist_size = max_value / bin_size;

        int[] arr = new int[array_count];
        int[] hist = new int[hist_size];
        for (int i = 0; i < array_count; i++) {
            arr[i] = (int) (Math.random() * max_value);
        }
        for (int i = 0; i < array_count; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();

        for (int i = 0; i < array_count; i++) {
            hist[arr[i] / bin_size]++;
        }
        for (int i = 0; i < hist_size; i++) {
            System.out.print(hist[i] + " ");
        }
        System.out.println();

        System.out.println();
        for (int i = 0; i < hist_size; i++) {
            int start = i * bin_size;
            int end = start + bin_size - 1;
            System.out.print(start + "~" + end + "\t\t");

            int count = hist[i] / display_scale;
            for (int k = 0; k < count; k++) {
                System.out.print("#");
            }
            System.out.println();
        }
    }
} ![Alt homework11](./images/homework10.png)

package homework;

public class homework11 {
    public static void main(String[] args) {
        int array_count;
        if (args.length == 1) {
            array_count = Integer.parseInt(args[0]);
        } else {
            array_count = 100;
        }

        int[] arr = new int[array_count];
        for (int i = 0; i < array_count; i++) {
            arr[i] = (int) (Math.random() * 100) + 1;
        }

        System.out.println("=== 생성된 데이터 ===");
        for (int i = 0; i < array_count; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println("\n");

        double sum = 0;
        for (int i = 0; i < array_count; i++) {
            sum += arr[i];
        }
        double arithmeticMean = sum / array_count;
        System.out.printf("arithmetic mean = %f\n", arithmeticMean);

        double logSum = 0;
        for (int i = 0; i < array_count; i++) {
            logSum += Math.log(arr[i]);
        }
        double geometricMean = Math.exp(logSum / array_count);
        System.out.printf("geometric mean  = %f\n", geometricMean);

        double reciprocalSum = 0;
        for (int i = 0; i < array_count; i++) {
            reciprocalSum += (1.0 / arr[i]);
        }
        double harmonicMean = array_count / reciprocalSum;
        System.out.printf("harmonic mean   = %f\n", harmonicMean);

        for (int i = 0; i < array_count - 1; i++) {
            int minIdx = i;
            for (int j = i + 1; j < array_count; j++) {
                if (arr[j] < arr[minIdx]) {
                    minIdx = j;
                }
            }
            int temp = arr[i];
            arr[i] = arr[minIdx];
            arr[minIdx] = temp;
        }

        double median;
        if (array_count % 2 == 1) {
            median = arr[array_count / 2];
        } else {
            median = (arr[(array_count / 2) - 1] + arr[array_count / 2]) / 2.0;
        }
        System.out.printf("median          = %f\n", median);
    }
}  ![Alt homework11](./images/homework11.png)

package homework;

import java.util.Scanner;

public class homework13 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.print("수식 입력 (종료: q) : ");
            String inputString = scanner.nextLine().trim();

            if (inputString.equalsIgnoreCase("q")) {
                break;
            }
            if (inputString.isEmpty()) {
                continue;
            }

            String[] arrOfStr = inputString.split(" ");

            if (arrOfStr.length == 3) {
                double num1 = Double.parseDouble(arrOfStr[0]);
                String op = arrOfStr[1];
                double num2 = Double.parseDouble(arrOfStr[2]);

                double result = calculate(num1, op, num2);
                System.out.println("결과: " + formatResult(result));

            } else if (arrOfStr.length == 5) {
                double num1 = Double.parseDouble(arrOfStr[0]);
                String op1 = arrOfStr[1];
                double num2 = Double.parseDouble(arrOfStr[2]);
                String op2 = arrOfStr[3];
                double num3 = Double.parseDouble(arrOfStr[4]);

                double result;
                // 곱셈(#) 및 나눗셈(/) 우선순위 처리
                if ((op2.equals("#") || op2.equals("/")) && !(op1.equals("#") || op1.equals("/"))) {
                    double temp = calculate(num2, op2, num3);
                    result = calculate(num1, op1, temp);
                } else {
                    double temp = calculate(num1, op1, num2);
                    result = calculate(temp, op2, num3);
                }
                System.out.println("결과: " + formatResult(result));

            } else {
                System.out.println("잘못된 입력 형식입니다. (예: 2 + 3 또는 2 + 4 # 7)");
            }
            System.out.println();
        }

        scanner.close();
    }

    public static double calculate(double a, String op, double b) {
        if (op.equals("+")) {
            return a + b;
        } else if (op.equals("-")) {
            return a - b;
        } else if (op.equals("#")) {
            return a * b;
        } else if (op.equals("/")) {
            if (b == 0) {
                System.out.println("0으로 나눌 수 없습니다.");
                return 0;
            }
            return a / b;
        }
        return 0;
    }

    public static String formatResult(double val) {
        if (val == (long) val) {
            return String.format("%d", (long) val);
        } else {
            return String.format("%.4f", val);
        }
    }
} ![Alt homework11](./images/homework13.png)
