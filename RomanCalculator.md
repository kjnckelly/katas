[Original Idea](https://codingdojo.org/kata/RomanCalculator/)

# Roman Calculator

## Problem Description
“As a Roman Bookkeeper I want to use a calculator to help with my math because doing it manually is too tedious.”
Using only the symbols for roman numerals, take two numbers and add them. 
An example would be “XIV” + “LX” = “LXXIV”

| **Symbol** | I | V | X  | L  | C   | D   | M    |
| ---------- | - | - | -- | -- | --- | --- | ---- |
| **Value**  | 1 | 5 | 10 | 50 | 100 | 500 | 1000 |

Roman numeral rules:
* Numbers are formed by combining several numerals. Example: “XXII” is twenty-two.
* If a lesser numeral is put before a bigger it means subtraction of the lesser from the bigger. Example: IV can be read as one less than five (4) and CM can be read one-hundred less than one-thousand (900)
* If the numeral is I, X or C you can’t have more than three. Example: “IIII” is invalid and should be “IV” and "LXXXX" should be "XC"
* If the numeral is V, L or D you can’t have more than one. Example: “DD” is invalid and should be “M”

## Constraints
As we are in Rome there is _no such thing as decimals or integers_, so **we need to do this with the strings**.
You need to write a function that takes two strings, and yields a string.  **Do not convert the string into an integer within your function.**

## Advanced
Also include functions in your calculator for subtraction, and multiplication.
