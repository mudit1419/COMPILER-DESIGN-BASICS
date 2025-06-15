# COMPILER-DESIGN-BASICS #
*COMPANY*: CODTECH IT SOLUTIONS
*NAME*: MUDIT KUMAR
*INTERN ID*: CT04DF877
*DOMAIN*: C++ PROGRAMMING
*DURATION*: 4 WEEKS
*MENTOR*: NEELA SANTOSH KUMAR


##DESCRIPTION## 

Simple Arithmetic Expression Evaluator
This project is a basic command-line arithmetic expression evaluator implemented in C++. It parses and evaluates mathematical expressions containing addition (+), subtraction (-), multiplication (*), division (/), decimal numbers, and parentheses for grouping. The program handles invalid inputs gracefully by providing descriptive error messages.

Features
Supports basic arithmetic operations: +, -, *, and /

Handles parentheses () for expression grouping

Accepts decimal numbers

Ignores whitespace in expressions

Detects and reports errors like unexpected characters, malformed numbers, and division by zero

How It Works
The core of the program is implemented in the Parser class, which is responsible for parsing and evaluating the input expression string.

Class: Parser
Constructor
cpp
Copy
Edit
explicit Parser(const std::string& expr)
Initializes the parser with the input expression string and sets the parsing position to the beginning of the string.

double parse()
Starts the parsing process. It invokes the expression() method to parse the entire input and checks if any unexpected characters remain. If the input contains extra or malformed characters, it throws an error.

Parsing Methods
These methods implement a recursive descent parser, a common parsing technique based on the grammar rules of arithmetic.

double expression()
Handles addition and subtraction. It starts by parsing a term, then looks for + or - operators followed by more terms, combining them as it goes.

double term()
Handles multiplication and division. It starts by parsing a factor, then looks for * or / operators followed by more factors. It ensures that division by zero is caught and reported.

double factor()
Handles parentheses and numbers. If it encounters an opening parenthesis (, it recursively calls expression() to evaluate the inner expression and expects a closing parenthesis ). Otherwise, it parses a number.

double number()
Parses a numeric value from the input string. It supports integers and floating-point numbers with a single decimal point. If multiple decimals are detected or if a number is expected but not found, it throws an error.

void skipWhitespace()
A utility function that skips over any whitespace characters in the input, allowing users to input expressions with spaces (e.g., 3 + 4 * (2 - 1)).

Main Function
cpp
Copy
Edit
int main()
The entry point of the program. It repeatedly prompts the user to enter an arithmetic expression. If the user types "exit", the loop terminates. Otherwise, it creates a Parser object with the input string, calls parse(), and prints the result. Any exceptions thrown during parsing are caught and printed as error messages.

Example Usage
bash
Copy
Edit
Simple Arithmetic Expression Evaluator (type 'exit' to quit)

Enter expression: 3 + 4 * 2
Result: 11

Enter expression: (1 + 2) * (3 + 4)
Result: 21

Enter expression: 3.5 + 2.1
Result: 5.6

Enter expression: 3 / 0
Error: Division by zero
Error Handling
The program throws and catches various runtime errors including:

Unexpected characters in the expression

Malformed numbers (e.g., 3..5)

Missing closing parentheses

Division by zero

These are all caught in the main loop and displayed to the user without crashing the program.

Conclusion
This simple expression evaluator demonstrates key principles of expression parsing using recursive descent. It's ideal for learning how to implement your own calculator or parser for arithmetic expressions. You can further extend it by adding support for more operations (like exponentiation), functions (like sin, cos), or variables.


**OUTPUT**
![Image](https://github.com/user-attachments/assets/e09af928-95bc-42fd-8d64-4cf5c460578b)

Building a GUI-based calculator

Conclusion
This C++ project demonstrates the construction of a robust arithmetic parser using recursive descent parsing. It accurately handles precedence, nested expressions, and error cases, offering a solid introduction to both parsing techniques and interactive command-line tools.
