# COMPILER-DESIGN-BASICS #
*COMPANY*: CODTECH IT SOLUTIONS
*NAME*: MUDIT KUMAR
*INTERN ID*: CT04DF877
*DOMAIN*: C++ PROGRAMMING
*DURATION*: 4 WEEKS
*MENTOR*: NEELA SANTOSH KUMAR


##DESCRIPTION## 

Overview
This project is a simple arithmetic expression evaluator implemented in C++. It reads mathematical expressions from the user input, parses them, and calculates their result. The evaluator supports the basic arithmetic operations: addition (+), subtraction (-), multiplication (*), division (/), and parentheses for grouping (()).

It is built using a recursive descent parser, a top-down parsing technique that processes the input string according to the grammar rules of arithmetic expressions. The parser handles operator precedence and supports floating-point numbers as well.

Features
Handles basic arithmetic: +, -, *, /

Supports parentheses to change precedence

Evaluates floating-point numbers (e.g., 3.14, 2.5 + (4.1 * 3))

Detects and reports syntax errors, such as:

Multiple decimal points in a number

Unexpected characters

Mismatched parentheses

Division by zero

Interactive REPL (Read-Eval-Print Loop) interface

Code Structure
The core functionality is encapsulated in a class called Parser. The main function handles user interaction and error display.

Class: Parser
The Parser class takes a string input representing an arithmetic expression and processes it using several private helper functions. These functions implement the parsing logic using recursive descent based on operator precedence.

Constructor
cpp
Copy
Edit
explicit Parser(const std::string& expr) : input(expr), pos(0) {}
Initializes the parser with an input string and sets the parsing position to the beginning of the string.

parse()
cpp
Copy
Edit
double parse();
Starts the parsing process by calling the top-level expression() method. It checks if any unexpected characters remain after parsing and throws an error if so.

Parsing Methods
Each parsing method corresponds to a level of the arithmetic grammar:

expression()
cpp
Copy
Edit
double expression();
Handles addition and subtraction. It starts by evaluating a term() and then continues consuming + or - operators followed by more terms.

term()
cpp
Copy
Edit
double term();
Handles multiplication and division. It begins by evaluating a factor() and then applies * or / to subsequent factors. Division by zero is checked and handled with an exception.

factor()
cpp
Copy
Edit
double factor();
Handles individual numbers or parenthetical sub-expressions. If it encounters a '(', it recursively calls expression() to evaluate the enclosed expression and expects a corresponding ')'.

number()
cpp
Copy
Edit
double number();
Parses a floating-point number. It detects and throws an error for multiple decimal points. It converts digits to a double while handling the decimal portion using a decreasing factor.

skipWhitespace()
cpp
Copy
Edit
void skipWhitespace();
Skips any whitespace characters to ensure clean token parsing. This allows users to input expressions with or without spaces.

Main Function
cpp
Copy
Edit
int main();
Provides an interactive interface where users can input expressions repeatedly until they type "exit". It uses std::getline() to read user input and passes it to the Parser class. Errors are caught using try-catch blocks and reported to the user.

Example Usage
yaml
Copy
Edit
Simple Arithmetic Expression Evaluator (type 'exit' to quit)

Enter expression: 2 + 3 * 4
Result: 14

Enter expression: (2 + 3) * 4
Result: 20

Enter expression: 10 / (5 - 5)
Error: Division by zero

Enter expression: 5.5.2 + 1
Error: Multiple decimals in number

Enter expression: 3 + 
Error: Expected number at position 4
Error Handling
The parser is designed to catch and report common syntax and runtime errors:

Unexpected characters are flagged if any input remains unparsed after the expression.

Multiple decimals in a number raise a descriptive error.

Mismatched parentheses are detected and reported.

Division by zero is explicitly checked before performing division.

Applications and Extensions
While this project is a simple calculator, it can serve as a foundation for more advanced features:

Adding support for variables and assignment (e.g., x = 5)

Supporting functions like sin(), cos(), sqrt()

Converting to postfix or abstract syntax tree (AST) format

**OUTPUT**
![Image](https://github.com/user-attachments/assets/e09af928-95bc-42fd-8d64-4cf5c460578b)

Building a GUI-based calculator

Conclusion
This C++ project demonstrates the construction of a robust arithmetic parser using recursive descent parsing. It accurately handles precedence, nested expressions, and error cases, offering a solid introduction to both parsing techniques and interactive command-line tools.
