# Coordinate Conversion Script (Rectangular <-> Polar)

## Connect
For questions, support, or feature requests, please join my [Discord server]([https://discord.gg/your_discord_invite_link](https://discord.gg/)).

<hr>

This JavaScript code provides functionality for converting coordinates between rectangular (Cartesian) and polar coordinate systems. It includes the following features:
(No code changes need to be made in the script it's self)

*   **Input Validation:** Checks for valid numerical inputs and the correct number of comma-separated values.
*   **Error Handling:** Displays user-friendly error messages for invalid inputs.
*   **Conversion Formulas:** Implements the standard formulas for both rectangular-to-polar and polar-to-rectangular conversions.
*   **Decimal Output:** Displays the converted coordinates with a precision of four decimal places.
*   **Fractional Output:** Displays the converted coordinates as fractions using the \`math.js\` library.
*   **Dynamic Display:** Updates the 'results' HTML element with the converted coordinates.

  Input forms at bottom

## Functions

### \`toFraction(number)\`

This function takes a number as input and converts it into a fractional representation using the \`math.js\` library.  It returns a string in the format "numerator/denominator".

### \`convertPolarToRect()\`

This function converts polar coordinates (radius, angle in degrees) to rectangular coordinates (x, y).

1.  **Retrieves Input:** Reads the radius and angle values from the 'polarInputVal' input field.  The input should be in the format "radius, angle".
2.  **Input Parsing:** Splits the input string into two parts based on the comma delimiter.
3.  **Input Validation:**
    *   Checks if exactly two values are provided.
    *   Verifies that the radius and angle are valid numbers.
4.  **Conversion:**
    *   Converts the angle from degrees to radians.
    *   Calculates the x and y coordinates using the following formulas:
        *   \`x = cos(angleRad) * radius\`
        *   \`y = sin(angleRad) * radius\`
5.  **Output Formatting:**
    *   Formats the x and y coordinates to four decimal places using \`toFixed(4)\`.
    *   Converts the x and y coordinates to fractions using the \`toFraction()\` function.
6.  **Result Display:** Updates the 'results' HTML element with the calculated x and y coordinates, displaying both the decimal and fractional representations.

### \`convertRectToPolar()\`

This function converts rectangular coordinates (x, y) to polar coordinates (radius, angle in degrees).

1.  **Retrieves Input:** Reads the x and y values from the 'rectInputVal' input field. The input should be in the format "x, y".
2.  **Input Parsing:** Splits the input string into two parts based on the comma delimiter.
3.  **Input Validation:**
    *   Checks if exactly two values are provided.
    *   Verifies that the x and y values are valid numbers.
4.  **Conversion:**
    *   Calculates the radius using the formula: \`r = sqrt(x^2 + y^2)\`
    *   Calculates the angle (theta) in radians using \`atan2(y, x)\`.  The result is then converted to degrees.
    *   Normalizes the angle to be within the range of 0 to 360 degrees.
5.  **Output Formatting:**
    *   Formats the radius and angle to four decimal places using \`toFixed(4)\`.
    *   Converts the radius and angle to fractions using the \`toFraction()\` function.
6.  **Result Display:** Updates the 'results' HTML element with the calculated radius and angle, displaying both the decimal and fractional representations.

## Dependencies

*   **math.js:** This library is used for converting numbers to fractions.  It is in assets/links file path and is accessed via relative path.

## Usage

1.  Include this JavaScript code and the \`math.js\` library in your HTML file.
2.  Create input fields with the IDs 'polarInputVal' and 'rectInputVal' for polar and rectangular coordinates, respectively.
3.  Create a 'div' element with the ID 'results' to display the conversion results.
4.  Call the \`convertPolarToRect()\` or \`convertRectToPolar()\` functions when the user submits the input.

## Input correction

* When using sqrt (square root) you need parenthisis around the number being sqrt -> sqrt(3)
* When using π you need to replace it with 'pi' -> pi
* If you use a mixed fraction, ensure you use the multiply symbole rather than leaveing a sapce -> 3*pi/2
* Here is a example of a input that uses all three -> 7, sqrt(3)*pi/6
