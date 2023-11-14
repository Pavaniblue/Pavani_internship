import java.util.Scanner;

public class Management {

    public static void main(String[] args) {
        String[] studentNames = new String[20];
        int[] studentGrades = new int[5];
        int numberOfStudents = 0;
        Scanner scanner = new Scanner(System.in);
        boolean isExit = false;

        while (!isExit) {
            System.out.println("Choose an option:");
            System.out.println("1. Add new student and their grade");
            System.out.println("2. View a list of students and their grades");
            System.out.println("3. Calculate and display the average grade of all students");
            System.out.println("4. Exit");

            int selectedOption = scanner.nextInt();

            switch (selectedOption) {
                case 1:
                    if (numberOfStudents < 5) {
                        System.out.println("Enter student name:");
                        String name = scanner.next();
                        System.out.println("Enter student grade:");
                        int grade = scanner.nextInt();
                        studentNames[numberOfStudents] = name;
                        studentGrades[numberOfStudents] = grade;
                        numberOfStudents++;
                    } else {
                        System.out.println("Class is full");
                    }
                    break;
                case 2:
                    System.out.println("Student Name \t\t Grade");
                    for (int i = 0; i < numberOfStudents; i++) {
                        System.out.println(studentNames[i] + "\t\t\t" + studentGrades[i]);
                    }
                    break;
                case 3:
                    int sum = 0;
                    for (int i = 0; i < numberOfStudents; i++) {
                        sum += studentGrades[i];
                    }
                    float average = (float) sum / numberOfStudents;
                    System.out.println("The average grade of all students is: " + average);
                    break;
                case 4:
                    isExit = true;
                    break;
                default:
                    System.out.println("Invalid option. Please choose again.");
                    break;
            }
        }

        scanner.close();
    }
}
