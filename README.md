<h1>Mural Calculator</h1>

<h2>Description</h2>
This program requests user input for details regarding the creation of a mural. Based on values of the inputs, the program will provide the costs of each variable and the total costs.
<br />


<h2>Used to create:</h2>

- <b>Visual Studio 2022</b> 


<h2>Screenshots:</h2>
<img src="https://github.com/JrewSimpson/Mural-Calculator/blob/987a86ece069c4f40915d2fb83de4d85bf780aca/Mural1.JPG" height="80%" width="80%" alt="]"/>
<img src="https://github.com/JrewSimpson/Mural-Calculator/blob/987a86ece069c4f40915d2fb83de4d85bf780aca/Mural2.JPG" height="80%" width="80%" alt="]"/>

<h2>Code:</h2>

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;

    namespace Program_1
    {
    internal class Program
    {
        static void Main(string[] args)
        {
            // Declared const double variables
            const double extra_per_ft = 0.10; // 10% of extra for waste
            const double lights_install= 75.00; // Cost of light install
            const double cost_per_paint_coat = 10.00; // Cost of paint per coat
            const double cost_per_color = 8.50; // Cost of each color of paint
            const double labor_cost_per_sq_ft = 6.50; // Cost of labor

            // Declared int variables which will take integer values from the user
            int numofColors; // Holds the number of colors as an integer
            int numofpaintcoats; // Holds number of paint coats
            int illumination; // Will hold 1 or 0, determines whether illumination will be used or not

            // Declared variables that take keyboard input from user
            double muralWidthFt; // Varible will store user input for mural width
            double muralLengthFt; // Varible will store user input for mural length
            double paintPricePerSqFt; // Varible will store user input for paint price per square foot

            // Declared variables that the program has to calculate
            double paintArea; // Will store the paint area calculation
            double paintCost; // Will store the paint cost calculation
            double laborCost; // Will store the labor cost calculation
            double coatsCost; // Will store the paint coats cost calculation
            double totalCost; // Will store the calculation of the total cost

            Console.WriteLine("Welcome to the Mural Calculator!");
            // User Inputs
            Console.Write("Enter the Width in ft: "); // Width Input
            muralWidthFt = double.Parse(Console.ReadLine());

            Console.Write("Enter the Length in ft: "); // Length Input
            muralLengthFt = double.Parse(Console.ReadLine());

            Console.Write("Enter the Price of Paint: "); // Price of Paint input
            paintPricePerSqFt = double.Parse(Console.ReadLine());

            Console.Write("How Many Coats of Paint Will be Used? (1 or 2): "); // Number of Coats of Paint input
            numofpaintcoats = int.Parse(Console.ReadLine());

            Console.Write("Enter the Number of Colors to Include: "); // Number of Colors of Paint input
            numofColors = int.Parse(Console.ReadLine());

            Console.Write("Will the Mural be Illuminated? (1 = Yes, 0= No): "); // Question of will the mural be illuminated or not
            illumination = int.Parse(Console.ReadLine());

            // Calculations
            paintArea = muralWidthFt * muralLengthFt; // Area of Paint calculation
            laborCost = illumination * lights_install + paintArea * labor_cost_per_sq_ft; // Total Labor Cost Calculation
            paintCost = paintArea * paintPricePerSqFt * (1+extra_per_ft) + numofColors * cost_per_color; // Total Paint Cost Calculation
            coatsCost = numofpaintcoats * cost_per_paint_coat; // Total Paint Coats Calculation
            totalCost = laborCost + paintCost + coatsCost; // Calculation of Total Costs

            //Display of Calculations
            Console.WriteLine($"Area of Mural in Square Ft: {paintArea:F1}"); // Displays Area of Mural
            //F1 causes the console to display 1 decimal digit after "."
            Console.WriteLine($"Paint Cost: {paintCost:C2}"); // Displays Paint Costs
            // C2 causes the console to display currency format with 2 decimal digits after "."
            Console.WriteLine($"Coats Cost: {coatsCost:C2}"); // Displays Coats Cost
            Console.WriteLine($"Labor Cost: {laborCost:C2}"); // Displays Labor Costs
            Console.WriteLine($"Total Cost: {totalCost:C2}"); // Displays the Total Costs
        }
    }
    }
