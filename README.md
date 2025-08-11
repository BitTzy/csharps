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

class Program
{
    static void Main()
    {
        Shape iskever = new Square("yellow", 10);
        Shape bilog = new Circle("green", 5);

        iskever.DisplayInfo();
        Console.WriteLine("Area: " + iskever.GetArea());

        bilog.DisplayInfo();
        Console.WriteLine("Area: " + bilog.GetArea());
    }
}
