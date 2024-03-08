import java.util.Scanner;
public class StudentGradeCalculator {
    public static void main(String[] args) {
        Scanner inputScanner = new Scanner(System.in);

        System.out.println("Enter the number of subjects: ");
        int numberofSubjects = inputScanner.nextInt();

        int totalMarks = 0;
        for(int subjectIndex =1; subjectIndex <= numberofSubjects; subjectIndex++){
            System.out.println("Enter the marks of the subject " + subjectIndex + " ( out of 100): ");
            int subjectMarks  = inputScanner.nextInt();
            totalMarks += subjectMarks;
        }
        double averagePercentage = (double) totalMarks / numberofSubjects;

        char grade = calculateGrade(averagePercentage);

        System.out.println("\nResults:");
        System.out.println("Total Marks: " + totalMarks);
        System.out.println("Average Percentage: " + averagePercentage + "%");
        System.out.println("Grade: " + grade);

        inputScanner.close();
    }
    private static char calculateGrade(double averagePercentage){
        if (averagePercentage >= 90){
            return  'A';
        } else if (averagePercentage >= 80) {
            return 'B';
        } else if(averagePercentage >= 70){
            return 'C';
        } else if (averagePercentage >= 60) {
            return 'D';
        }else {
            return 'F';
        }
    }
}
