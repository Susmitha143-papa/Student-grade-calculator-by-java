# Student-grade-calculator-by-java
import java.util.Scanner;

public class StudentResults {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input: Number of subjects
        System.out.print("Enter the number of subjects: ");
        int numSubjects = scanner.nextInt();
        
        // Array to store marks
        int[] marks = new int[numSubjects];
        
        // Input: Marks obtained in each subject
        for (int i = 0; i < numSubjects; i++) {
            System.out.print("Enter marks obtained in subject " + (i + 1) + " (out of 100): ");
            marks[i] = scanner.nextInt();
        }

        // Calculate total marks
        int totalMarks = 0;
        for (int i = 0; i < numSubjects; i++) {
            totalMarks += marks[i];
        }

        // Calculate average percentage
        double averagePercentage = (double) totalMarks / (numSubjects * 100) * 100;

        // Determine the grade based on the average percentage
        String grade;
        if (averagePercentage >= 90) {
            grade = "A";
        } else if (averagePercentage >= 75) {
            grade = "B";
        } else if (averagePercentage >= 60) {
            grade = "C";
        } else if (averagePercentage >= 50) {
            grade = "D";
        } else {
            grade = "F";
        }

        // Display Results
        System.out.println("\n--- Results ---");
        System.out.println("Total Marks: " + totalMarks + "/" + (numSubjects * 100));
        System.out.printf("Average Percentage: %.2f%%\n", averagePercentage);
        System.out.println("Grade: " + grade);
        
        scanner.close();
    }
}
