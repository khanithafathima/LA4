import java.util.Scanner;

public class Calculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to the Calculator!");
        System.out.print("Enter the first number: ");
        double num1 = scanner.nextDouble();

        System.out.print("Enter the second number: ");
        double num2 = scanner.nextDouble();

        System.out.print("Enter an operator (+, -, *, /): ");
        char operator = scanner.next().charAt(0);

        double result = calculate(num1, num2, operator);

        if (Double.isNaN(result)) {
            System.out.println("Invalid operator or division by zero");
        } else {
            System.out.println("Result: " + result);
        }
    }

    public static double calculate(double num1, double num2, char operator) {
        switch (operator) {
            case '+':
                return num1 + num2;
            case '-':
                return num1 - num2;
            case '*':
                return num1 * num2;
            case '/':
                if (num2 != 0) {
                    return num1 / num2;
                } else {
                    return Double.NaN; // Indicate division by zero with NaN (Not-a-Number)
                }
            default:
                return Double.NaN; // Invalid operator
        }
    }
}
