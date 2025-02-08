import java.util.Arrays;
import java.util.Scanner;

public class STGrade 
{

    public static void main(String[] args) {
        Scanner obj = new Scanner(System.in);
        int min,max,i, sum = 0;
        System.out.println("Enter the number of students: ");
        int n = obj.nextInt();
        
        int StdMarks[] = new int[n];
        min = StdMarks[0];
        max = StdMarks[0];
        for (i = 0; i < n; i++) 
        {
            System.out.println("Enter marks for student " + (i + 1) + ": ");
            StdMarks[i] = obj.nextInt();
            sum = sum + StdMarks[i];
        }
        System.out.println("total Marks of students " + sum);
        double avg = sum/n;
        System.out.println("Average Marks of students " + avg);
        

    System.out.println("The minimum marks scored by student :" + Arrays.stream(StdMarks).max().getAsInt());

    System.out.println("The maximum marks scored by student :" + Arrays.stream(StdMarks).min().getAsInt());


        obj.close();


        for (int marks : StdMarks) 
        {
            char grade = calculateGrade(marks);
            System.out.println("Student with marks " + marks + " have grade: " + grade);
        }
        
    }

    public static char calculateGrade(int marks) {
        if (marks >= 90) 
        {
            return 'A';
        } 
        else if (marks >= 80) 
        {
            return 'B';
        } 
        else if (marks >= 70) 
        {
            return 'C';
        } 
        else if (marks >= 60) 
        {
            return 'D';
        }
         else 
        {
            return 'F';
        }
    }
}
