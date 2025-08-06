# csharps
xv
using System;
using System.Linq;

public abstract class Student
{
    public string Name { get; set; }
    protected double[] grades;

    public abstract void SetData();
    public abstract void DisplayInfo();
    public abstract void CheckStatus();
}

public class CollegeStudent : Student
{
    public override void SetData()
    {
        Console.WriteLine("\n--- Entering College Student Data ---");
        Console.Write("Enter Name: ");
        Name = Console.ReadLine();

        grades = new double[3];
        for (int i = 0; i < 3; i++)
        {
            Console.Write($"Enter grade for subject {i + 1}: ");
            while (!double.TryParse(Console.ReadLine(), out grades[i]) || grades[i] < 0 || grades[i] > 100)
            {
                Console.WriteLine("Invalid input. Please enter a number between 0 and 100.");
                Console.Write($"Enter grade for subject {i + 1}: ");
            }
        }
    }

    public override void DisplayInfo()
    {
        Console.WriteLine("\n--- College Student Information ---");
        Console.WriteLine($"Name: {Name}");
        Console.WriteLine($"Grades: {string.Join(", ", grades)}");
    }

    public override void CheckStatus()
    {
        double average = grades.Average();
        Console.WriteLine($"Average Grade: {average:F2}");
        if (average >= 75)
        {
            Console.WriteLine("Status: Passed");
        }
        else
        {
            Console.WriteLine("Status: Failed");
        }
    }
}

public class SeniorStudent : Student
{
    public override void SetData()
    {
        Console.WriteLine("\n--- Entering Senior High Student Data ---");
        Console.Write("Enter Name: ");
        Name = Console.ReadLine();

        grades = new double[1];
        Console.Write("Enter final grade: ");
        while (!double.TryParse(Console.ReadLine(), out grades[0]) || grades[0] < 0 || grades[0] > 100)
        {
            Console.WriteLine("Invalid input. Please enter a number between 0 and 100.");
            Console.Write("Enter final grade: ");
        }
    }

    public override void DisplayInfo()
    {
        Console.WriteLine("\n--- Senior High Student Information ---");
        Console.WriteLine($"Name: {Name}");
        Console.WriteLine($"Final Grade: {grades[0]}");
    }

    public override void CheckStatus()
    {
        if (grades[0] >= 75)
        {
            Console.WriteLine("Status: Passed");
        }
        else
        {
            Console.WriteLine("Status: Failed");
        }
    }
}

public class Program
{
    public static void Main(string[] args)
    {
        Console.WriteLine("===== Student Status Checker (OOP Console 2) =====");

        Console.WriteLine("\nProcessing College Student...");
        Student collegeStudent = new CollegeStudent();
        collegeStudent.SetData();
        collegeStudent.DisplayInfo();
        collegeStudent.CheckStatus();

        Console.WriteLine("\n" + new string('=', 50) + "\n");

        Console.WriteLine("Processing Senior High Student...");
        Student seniorStudent = new SeniorStudent();
        seniorStudent.SetData();
        seniorStudent.DisplayInfo();
        seniorStudent.CheckStatus();

        Console.WriteLine("\n\nProgram finished. Press any key to exit.");
        Console.ReadKey();
    }
}
