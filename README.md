# Simple-Java-Calculator
A basic calculator using static and non-static methods



import java.util.Scanner;

public class Calculator {

    public static void greetUser() {
        System.out.println("Welcome to Simple Calculator!");
    }

    public static int add(int a, int b) {
        return a + b;
    }
    public static int multiply(int a, int b) {
        return a * b;
    }

    public void displayMenu() {
        System.out.println("Choose an operation:");
        System.out.println("1. Addition");
        System.out.println("2. Subtraction");
        System.out.println("3. Multiplication");
        System.out.println("4. Division");
        System.out.println("5. Exit");
    }

    public int subtract(int a, int b) {
        return a - b;
    }
     public double divide(int a, int b) {
        if (b == 0) {
            System.out.println("❌ Cannot divide by zero.");
            return Double.NaN;
        }
        return (double) a / b;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        greetUser();

        Calculator calc = new Calculator();

        while (true) {
            calc.displayMenu();
            System.out.print("Enter your choice: ");
            int choice = sc.nextInt();

            if (choice == 5) {
                System.out.println("Exiting...");
                break;
            }

            System.out.print("Enter two numbers: ");
            int x = sc.nextInt();
            int y = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.println("Sum = " + add(x, y));
                    break;
                case 2:
                    System.out.println("Difference = " + calc.subtract(x, y));
                    break;
                case 3:
                    System.out.println("Product = " + multiply(x, y));
                    break;
                case 4:
                    double result = calc.divide(x, y);
                    if (!Double.isNaN(result)) {
                        System.out.println("Quotient = " + result);
                    }
                    break;
                default:
                    System.out.println("Invalid choice!");
            }

            System.out.println("--------------------------");
        }

        sc.close();
    }
}

