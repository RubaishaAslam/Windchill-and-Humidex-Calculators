# school
CS 1026B – Assignment 1

Windchill and Humidex Calculators


Overview

Write a program using user input, loops, and conditionals to calculate the windchill or humidex.

Background

There are two measurements used in Canada used to indicate the difference between the actual air
temperature and what it “feels like”. In the summer, the humidex gives an indication of how humidity
affects how hot it feels. In the winter, the windchill indicates how wind speed affects how cold it feels.
These measurements are calculated using formulas:
Measurement Variables used Formula
Humidex (H) D: dew point (deg C)
T: air temperature (deg C)
F = 6.11 * e(5417.7530 * ( 1/273.16 – 1 / (273.16 + D ) ) )
G = 5/9 * (F – 10)
H = T + G
Windchill (W) v: wind velocity (km/h)
T: air temperature (deg C)
W = 13.12 + 0.6125 * T – 11.37 * v0.16 + 0.3965 * T * v0.16
In the formula for humidex, e is Euler’s number (approximately 2.71828). In the math module, this can
be accessed using the math.exp() function, i.e., to calculate et
for some value t, write math.exp(t).
Note that we will assume that the dew point is always less than or equal to the air temperature.
Environment Canada provides a calculator for these two measurements online at
https://weather.gc.ca/windchill/wind_chill_e.html. Note that this website may differ from the formula
for extreme values (e.g., very low windspeeds). The website is provided for reference only and the
formula is always considered the correct value. 
Additionally, Environment Canada provides guides for both measurements (these are slightly adapted).
Humidex
Humidex Range Comfort rating
20 to 29 Little or no discomfort
30 to 39 Some discomfort
40 to 44 Great discomfort. Avoid exertion
Above 45 Dangerous. Heat stroke possible
Wind chill
Wind chill range Exposure Risk
0 to -9 Low risk
-10 to -27 Moderate risk
-28 to -39 High Risk. Skin can freeze in 10-30 minutes
Below -40 Very High Risk. Skin can in under 10 minutes
In this assignment, you will write a program in python that prompts the user for information and then
displays the appropriate measurement. In particular:
1. You should ask the user for the (air) temperature. The temperature should be allowed to be a
floating point number, but you can assume that the user types a valid number (no letters or
other non-number characters). If the user types a value outside the range of typical values in
Canada (less than -50 or greater than +50), prompt for the user to enter a new value until an
appropriate value is entered.
2. If appropriate, you should calculate the windchill or humidex. Prompt the user for the additional
information needed, under these conditions:
a. Report the windchill if the temperature is 0 or below, as well as the exposure risk.
Windchill should be reported as a whole number (rounded to the nearest integer using
round(), i.e., with round(x)).
b. Report the humidex if the temperature is 20 or above, as well as the comfort rating.
Humidex should be reported as a whole number (rounded from the formula provided).
c. If neither of the conditions is true at the temperature, report this to the user and
continue.
For wind speeds, the input can be a floating point and should be in the range from 1 to 99 km/h
(inclusive). For dew point, the temperature must fall in the same range as the air temperature
and must also be less than or equal to the air temperature. In both cases, if these conditions are
not met, the user should be prompted for a new value until an appropriate value is entered.
3. After reporting the outcome, ask the user if they would like to continue with a Y/N question. If
the user wants to continue, then you should prompt for temperature again and continue. If the
user wants to quit, the program should end. The prompt should work correctly when the
answer the user gives starts with an Y or N (upper or lower case). If any other character is
entered as the first character, the user should be prompted again.
To help make sure your code behaves exactly as specified, a text file with all the prompts has been
provided. You should copy these into your code to prevent typos in your submission. Follow the format
precisely to avoid lost marks due to automated grading. Do not put any extra blank lines in your output.



Example Execution

The following sample run of the program is provided for your reference only. It is not a complete
example of all possible cases. You should design your own test cases to ensure your code is working.
Enter a temperature between -50 and 50: -30
Calculating windchill.
Enter a wind speed between 1 and 99 km/h: 15
The windchill is -41. Very High Risk. Skin can freeze in under 10 minutes.
Check another weather condition (Y/N)? y
Enter a temperature between -50 and 50: 25
Calculating humidex.
Enter the dewpoint between -50 and 50: 24
The humidex is 36. Some discomfort.
Check another weather condition (Y/N)? Y
Enter a temperature between -50 and 50: 15
Windchill and humidex are not a factor at this temperature.
Check another weather condition (Y/N)? n
Process finished with exit code 0
