# temperature-conversion-cpp
C++ Console Application that converts between Celsius, Fahrenheit, and Kelvin
Temperature Conversion Application
Author: VinDeli
Repository: https://github.com/VinDeli/temperature-conversion-cpp
Language: C++
IDE: Visual Studio 2022
 Project Overview
A C++ console application that performs temperature conversions between Celsius, Fahrenheit, and Kelvin. This project demonstrates fundamental programming concepts including user input validation, mathematical calculations, and menu-driven program design.
 Features

Multi-Unit Conversion: Convert between Celsius, Fahrenheit, and Kelvin
Interactive Menu: User-friendly console interface with clear options
Input Validation: Robust error handling for invalid user inputs
Precision Control: Accurate floating-point calculations with proper formatting
Continuous Operation: Option to perform multiple conversions without restarting

 Technology Stack

Language: C++17
IDE: Visual Studio 2022 (v17.13)
Platform: Windows (x86/x64)
Build System: MSBuild (Visual Studio Project)

 Project Structure
temperature-conversion-cpp/
├── TemperatureConversion.sln          # Visual Studio Solution File
├── TemperatureConversion/
│   ├── TemperatureConversion.vcxproj   # Visual Studio Project File
│   ├── TemperatureConversion.cpp       # Main application source code
│   ├── TempConverter.h                 # Header file for conversion functions
│   └── TempConverter.cpp               # Implementation of conversion logic
├── README.md                           # Project documentation
└── .gitignore                          # Git ignore file for C++/VS
🔧 Setup & Installation
Prerequisites

Visual Studio 2022 (Community, Professional, or Enterprise)
C++ Development Tools (installed with Visual Studio)
Windows SDK (typically included with Visual Studio)

Build Instructions

Clone Repository
bashgit clone https://github.com/VinDeli/temperature-conversion-cpp.git
cd temperature-conversion-cpp

Open in Visual Studio

Double-click TemperatureConversion.sln
Or open Visual Studio → File → Open → Project/Solution


Build Project

Press Ctrl + Shift + B or
Build → Build Solution
Or right-click solution → Build


Run Application

Press F5 (Debug mode) or Ctrl + F5 (Release mode)
Or Debug → Start Debugging/Start Without Debugging



Command Line Build (Alternative)
bash# Using Developer Command Prompt for VS 2022
msbuild TemperatureConversion.sln /p:Configuration=Release /p:Platform=x64
 Usage
Sample Program Flow
=== Temperature Conversion Tool ===

Select conversion type:
1. Celsius to Fahrenheit
2. Celsius to Kelvin
3. Fahrenheit to Celsius
4. Fahrenheit to Kelvin
5. Kelvin to Celsius
6. Kelvin to Fahrenheit
7. Exit

Enter your choice (1-7): 1
Enter temperature in Celsius: 25
25.00°C = 77.00°F

Continue? (y/n): y
Conversion Formulas Implemented

Celsius to Fahrenheit: F = (C × 9/5) + 32
Celsius to Kelvin: K = C + 273.15
Fahrenheit to Celsius: C = (F - 32) × 5/9
Fahrenheit to Kelvin: K = (F - 32) × 5/9 + 273.15
Kelvin to Celsius: C = K - 273.15
Kelvin to Fahrenheit: F = (K - 273.15) × 9/5 + 32

 Example Code Structure
Main Application (TemperatureConversion.cpp)
cpp#include <iostream>
#include <iomanip>
#include "TempConverter.h"

int main() {
    int choice;
    double temperature, result;
    char continueChoice;
    
    do {
        displayMenu();
        choice = getUserChoice();
        
        if (choice >= 1 && choice <= 6) {
            temperature = getTemperatureInput();
            result = performConversion(choice, temperature);
            displayResult(choice, temperature, result);
        }
        
        if (choice != 7) {
            continueChoice = askToContinue();
        }
        
    } while (choice != 7 && continueChoice == 'y');
    
    return 0;
}
Conversion Functions (TempConverter.h)
cpp#pragma once

class TempConverter {
public:
    static double celsiusToFahrenheit(double celsius);
    static double celsiusToKelvin(double celsius);
    static double fahrenheitToCelsius(double fahrenheit);
    static double fahrenheitToKelvin(double fahrenheit);
    static double kelvinToCelsius(double kelvin);
    static double kelvinToFahrenheit(double kelvin);
    
    static void displayMenu();
    static int getUserChoice();
    static double getTemperatureInput();
    static void displayResult(int choice, double input, double result);
};
 Learning Objectives Demonstrated
Programming Concepts

Functions and Modular Design: Separated conversion logic into reusable functions
Input Validation: Robust handling of user input with error checking
Control Structures: Loops, conditional statements, and switch cases
Data Types: Proper use of integers, doubles, and characters
Headers and Implementation: Separation of interface and implementation

C++ Specific Features

Class Design: Static methods for utility functions
Stream I/O: Using iostream for console input/output
Precision Control: std::setprecision() for formatted output
Memory Management: Stack-based variables and automatic cleanup

Software Engineering Practices

Code Organization: Logical file structure and clear naming conventions
Error Handling: Graceful handling of invalid inputs
User Experience: Clear prompts and formatted output
Documentation: Comprehensive comments and documentation

 Key Features Implemented
Input Validation
cppint TempConverter::getUserChoice() {
    int choice;
    while (!(std::cin >> choice) || choice < 1 || choice > 7) {
        std::cout << "Invalid input. Please enter a number between 1-7: ";
        std::cin.clear();
        std::cin.ignore(10000, '\n');
    }
    return choice;
}
Precision Formatting
cppvoid TempConverter::displayResult(int choice, double input, double result) {
    std::cout << std::fixed << std::setprecision(2);
    // Format and display conversion results with appropriate units
}
 Future Enhancements

 GUI Interface: Windows Forms or Qt-based graphical interface
 Batch Conversion: Process multiple temperatures from file input
 Additional Units: Rankine, Réaumur, and other temperature scales
 History Feature: Save and display previous conversions
 Configuration: User preferences for default precision and units
 Unit Tests: Comprehensive testing framework with Google Test
 Internationalization: Multiple language support

 Testing
Manual Test Cases

Valid Conversions: Test all 6 conversion types with known values
Edge Cases: Test absolute zero, freezing/boiling points of water
Invalid Input: Test non-numeric input, out-of-range values
Menu Navigation: Test all menu options and exit functionality

Sample Test Values
InputExpected OutputActual OutputStatus0°C → °F32.00°F32.00°F Pass100°C → °F212.00°F212.00°F Pass-273.15°C → K0.00K0.00K Pass
Educational Value
This project serves as an excellent introduction to C++ programming, demonstrating:

Problem Decomposition: Breaking complex problems into manageable functions
Algorithm Implementation: Converting mathematical formulas to code
User Interface Design: Creating intuitive console-based interactions
Code Quality: Writing maintainable, readable, and well-documented code

Contributing
This project was developed for educational purposes. To contribute:

Fork the repository
Create a feature branch (git checkout -b feature/new-feature)
Commit changes (git commit -am 'Add new feature')
Push to branch (git push origin feature/new-feature)
Create a Pull Request

License
This project is developed for educational purposes as part of coursework. Please refer to your institution's academic integrity policies regarding code sharing and collaboration.
Academic Context
Institution: Southern New Hampshire University


Repository Link: https://github.com/VinDeli/temperature-conversion-cpp
Live Demo: https://vindeli.github.io/temperature-conversion-cpp/demo.html
