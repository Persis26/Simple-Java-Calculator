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

    public void displayMenu() {
        System.out.println("Choose an operation:");
        System.out.println("1. Addition");
        System.out.println("2. Subtraction");
        System.out.println("3. Exit");
    }

    public int subtract(int a, int b) {
        return a - b;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        greetUser();

        Calculator calc = new Calculator();

        while (true) {
            calc.displayMenu();
            System.out.print("Enter your choice: ");
            int choice = sc.nextInt();

            if (choice == 3) {
                System.out.println("Exiting...");
                break;
            }

            System.out.print("Enter two numbers: ");
            int x = sc.nextInt();
            int y = sc.nextInt();

            if (choice == 1) {
                int result = add(x, y);
                System.out.println("Sum = " + result);
            } else if (choice == 2) {
                int result = calc.subtract(x, y);
                System.out.println("Difference = " + result);
            } else {
                System.out.println("Invalid choice!");
            }

            System.out.println("--------------------------");
        }

        sc.close();
    }
}

