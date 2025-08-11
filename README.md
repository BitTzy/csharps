using System;

abstract class Shape
{
    // Property
    public string Color { get; set; }

    // Constructor
    public Shape(string color)
    {
        Color = color;
        Console.WriteLine("Shape created");
    }

    // Destructor
    ~Shape()
    {
        Console.WriteLine("Shape destroyed");
    }

    // Abstract method (must be overridden in derived classes)
    public abstract double GetArea();

    // Virtual method (optional override)
    public virtual void DisplayInfo()
    {
        Console.WriteLine($"Color: {Color}");
    }
}

class Square : Shape
{
    public double SideLength { get; set; }

    public Square(string color, double sideLength) : base(color)
    {
        SideLength = sideLength;
    }

    public override double GetArea()
    {
        return SideLength * SideLength;
    }

    public override void DisplayInfo()
    {
        base.DisplayInfo();
        Console.WriteLine($"Square with side length: {SideLength}");
    }
}

class Circle : Shape
{
    public double Radius { get; set; }

    public Circle(string color, double radius) : base(color)
    {
        Radius = radius;
    }

    public override double GetArea()
    {
        return Math.PI * Radius * Radius;
    }

    public override void DisplayInfo()
    {
        base.DisplayInfo();
        Console.WriteLine($"Circle with radius: {Radius}");
    }
}
/workspaces/csharps/csharps/Program.cs(3,16): error CS0101: The namespace '<global namespace>' already contains a definition for 'Shape' [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(31,7): error CS0101: The namespace '<global namespace>' already contains a definition for 'Square' [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(52,7): error CS0101: The namespace '<global namespace>' already contains a definition for 'Circle' [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(9,12): error CS0111: Type 'Shape' already defines a member called 'Shape' with the same parameter types [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(16,6): error CS0111: Type 'Shape' already defines a member called '~Shape' with the same parameter types [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(22,28): error CS0111: Type 'Shape' already defines a member called 'GetArea' with the same parameter types [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(25,25): error CS0111: Type 'Shape' already defines a member called 'DisplayInfo' with the same parameter types [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/aksjdh.cs(31,7): error CS0534: 'Square' does not implement inherited abstract member 'Shape.GetArea()' [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(35,12): error CS0111: Type 'Square' already defines a member called 'Square' with the same parameter types [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(40,28): error CS0111: Type 'Square' already defines a member called 'GetArea' with the same parameter types [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(45,26): error CS0111: Type 'Square' already defines a member called 'DisplayInfo' with the same parameter types [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/aksjdh.cs(52,7): error CS0534: 'Circle' does not implement inherited abstract member 'Shape.GetArea()' [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(56,12): error CS0111: Type 'Circle' already defines a member called 'Circle' with the same parameter types [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(61,28): error CS0111: Type 'Circle' already defines a member called 'GetArea' with the same parameter types [/workspaces/csharps/csharps/csharps.csproj]
/workspaces/csharps/csharps/Program.cs(66,26): error CS0111: Type 'Circle' already defines a member called 'DisplayInfo' with the same parameter types [/workspaces/csharps/csharps/csharps.csproj]

The build failed. Fix the build errors and run again.
