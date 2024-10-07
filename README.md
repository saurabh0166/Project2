public class Task_2 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input: Take marks obtained (out of 100) in each subject.
        System.out.println("Enter marks obtained in each subject (out of 100):");
        int numSubjects = 0;
        int totalMarks = 0;

        // Calculate Total Marks: Sum up the marks obtained in all subjects.
        while (true) {
            System.out.print("Subject " + (numSubjects + 1) + " marks: ");
            int marks = scanner.nextInt();

            // Input validation: marks should be between 0 and 100
            if (marks < 0 || marks > 100) {
                System.out.println("Marks should be between 0 and 100. Please try again.");
                continue;
            }

            totalMarks += marks;
            numSubjects++;

            // Check if all subjects marks are inputted
            System.out.print("Do you have more subjects? (yes/no): ");
            String moreSubjects = scanner.next().toLowerCase();
            if (moreSubjects.equals("no")) {
                break;
            }
        }

        // Calculate Average Percentage: Divide the total marks by the total number of subjects to get the average percentage.
        double averagePercentage = (double) totalMarks / numSubjects;

        // Grade Calculation: Assign grades based on the average percentage achieved.
        char grade;
        if (averagePercentage >= 90) {
            grade = 'A';
        } else if (averagePercentage >= 80) {
            grade = 'B';
        } else if (averagePercentage >= 70) {
            grade = 'C';
        } else if (averagePercentage >= 60) {
            grade = 'D';
        } else {
            grade = 'F';
        }

        // Display Results: Show the total marks, average percentage, and the corresponding grade to the user
        System.out.println("Total Marks: " + totalMarks);
        System.out.println("Average Percentage: " + averagePercentage);
        System.out.println("Grade: " + grade);

        scanner.close();
    }
}
