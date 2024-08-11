public class EmployeePayCalculator {

    public static void main(String[] args) {
        // Test data
        double basePay = 9.0;
        int hoursWorked = 45;

        // Calculate and display the pay
        double totalPay = calculatePay(basePay, hoursWorked);
        if (totalPay != -1) {
            System.out.printf("Total pay for the week: $%.2f%n", totalPay);
        }
    }

    public static double calculatePay(double basePay, int hoursWorked) {
        // Define constants
        double MIN_WAGE = 8.00;
        int MAX_HOURS = 60;
        int REGULAR_HOURS = 40;
        double OVERTIME_RATE = 1.5;

        // Check for errors
        if (basePay < MIN_WAGE) {
            System.out.println("Error: Base pay is below the minimum wage.");
            return -1;
        }
        if (hoursWorked > MAX_HOURS) {
            System.out.println("Error: Hours worked exceed the limit of 60 hours.");
            return -1;
        }

        // Calculate regular and overtime pay
        double regularPay = Math.min(hoursWorked, REGULAR_HOURS) * basePay;
        double overtimePay = 0.0;

        if (hoursWorked > REGULAR_HOURS) {
            overtimePay = (hoursWorked - REGULAR_HOURS) * basePay * OVERTIME_RATE;
        }

        // Return total pay
        return regularPay + overtimePay;
    }
}
"C:\Users\BIDAL JOSEPH\.jdks\openjdk-22.0.2\bin\java.exe" "-javaagent:C:\Program Files\JetBrains\IntelliJ IDEA Community Edition 2024.1.4\lib\idea_rt.jar=50249:C:\Program Files\JetBrains\IntelliJ IDEA Community Edition 2024.1.4\bin" -Dfile.encoding=UTF-8 -Dsun.stdout.encoding=UTF-8 -Dsun.stderr.encoding=UTF-8 -classpath "C:\Users\BIDAL JOSEPH\.jdks\Helloworld.java\out\production\Helloworld.java" EmployeePayCalculator
Total pay for the week: $427.50

Process finished with exit code 0
