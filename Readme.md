#Assignment 1
Class: Monom.
Constructors:
Monom(double a, double b):
This constructor will initial a monom with the values given inside the arguments while a is our coefficient and b is our power.

Monom(Monom mot):
This constructor will initial a monom from a given monom.

Monom(String s): 
first we check if the char ‘x’ is in the string. If so, we take the chars before the ‘x’ and ask if there are real numbers attached to it. If not, we set our coefficient variable ‘doubleCoeff’ to 1. If there are real numbers attached to ‘x’ we take and convert them into doubles.  In case we have the char ‘-‘ only without any real numbers attached to it, we set our ‘doubleCoeff’ to -1. After we check if the char ‘^’ is in the string. If so, we take the chars after ‘^’ and convert them into integers. If he doesn’t appear, we set our power variable ‘pow’ to 1. In case both chars ‘x’ & ‘-‘ doesn’t appear in the string, we simple convert the string into doubles.

Methods:
Public void add(Monom m):
We check if the powers are equals, if so, we add between the two coefficients and set the that value as our new coefficient.
If not, we throw a new exception, that says that we had an error trying to add between those two monoms due to a different power values.

Public void multiply(Monom d):
First, we multiply between the two monoms coefficients.
Then we check if either of the monoms power is equal to 0, if so, we don’t change the power. If its not equal to 0, then we add between the monoms power.




Public String toString():
First, we check if our coefficient is equal to 1. If so, we set our string variable ‘ans’ to ‘x^’+power. the same thing we do with 
-1, except now we will output ‘-x^’+power. In case the power is 0, we will only output our coefficient. In case the power is 1, we will output our coefficient+’x’. in any other case we will simply output the string: coefficient +’x^’ + power.

Public boolean equals(Monom m):
We check if Monom ‘m’ coefficient and power is equal to our Monom coefficient and power. If so, we return true. Else we return false.

Public Monom copy():
This this function creates a deep copy of a monom.

Class: Polynom.
Constructors:
Polynom():
This constructor will initial a new Array List  called “poly” which represent our polynom.

Public Polynom(String str):
This constructor will initial a polynom from a given String. It will create a new Array List and a private method called “init_from_string” which will create a polynom from a given string. At the end we will add this polynom with the method “add”.

Methods:
Public double f(double x):
This method returns the values of y for a certain x.
We used an Iteretor of Monoms in order to go over our Array List(Polynom).

Public void add(Polynom_able p1):
This method gets an Polynom_able as an argument and we used an iteretor in order to go over the Array List (Polynom) and in each iteration we add the current monom.
In the end we activate a private function called removeZero which removes from the Polynom all the monoms that are the zero monom.
Public void add(Monom m1):
This method adds a monom to the polynom. If the monom equals to zero- and
the polynom is empty the function will add the zero monom else it does
nothing. . If the power of the monom equals to an existing monom , the
function will add them together. else the function adds the monom to the
polynom array. In the end the function sort the polynom by powers.

Public void substract(Polynom_able p1):
This method will subtract a given argument polynom from (this) polynom.
It will create a temp Polynom and add (this) monoms to it, after that it will go over p1(given argument) and add his monoms to the temp polynom multiplied by minus 1 which is basically what subtract means. 
At the end we clear our current list and build it again from the temp polynom which is the answer. Then we sort our list(our polynom) and again run our private method removeZero.

Public void multiply(Polynom_able p1):
This method receives a polynomial p1 and multiplies it with (this). If one of the polynomial is empty the function will add the second polynomial to the empty one. If one of the polynomial equals to zero, the function will return zero. Else the function will multiply the monomial of each polynomial in mathematical order , put the answer in a new polynomial and deep copy it into (this).

Public void multiply(Monom m1):
This method will multiply a polynom by a given monom.
It uses the method multiply from the Monom class for each monom in our polynom.

Public boolean equals(Polynom_able p1):
This method test if (this) polynom Is logically equal to p1.
Return false in case they are different.

Public boolean isZero():
This method return true if this polynom contains only the zero monom.
Public double root(double x0, double x1, double eps):
The method root finds a solution to the function f(x)=0 between 2 points.
This method receive x0 and x1 such as f(x0) and f(x1) must be from the opposite side of x-line else the method will throw Run time Exception. This method receive   x0 and x1 such as x0 need to be smaller then x1 else the method will throw Run time Exception.

Public Polynom_able copy():
This method creates a deep copy of the object.

Public Polynom_able derivative():
This method returns the derivative polynom.

Public double area(double x0, double x1, double eps):
Compute Riemann's Integral over this Polynom starting from x0, till x1 using
eps size steps. The function received x0 and x1 such as x0 need to be smaller
then x1 else the function returns area = 0. return the approximated area above the x-axis below this Polynom and between the [x0,x1] range.

Public String toString():
This method prints the polynom as: a0+a1x+a2x^2+…+anx^n.

Private Methods:
Private void removeZero():
This method moves over the polynom and checks two things:
1.If this is the zero polynom do nothing.
2.If the polynom contains more then one monom and one of them is the zero monom, remove him.

Private void init_from_string(String s):
This private method will initial a polynom from a given String. allowed chars are: 0,1,2,3,4,5,6,7,8,9,+,-,.,x,^ No spaces allowed. When a is a real number and b is a positive integer (natural) number. a can be positive or negative , b must be
positive. Constructing a new Polynom with string: The string must be written as such:"ax^b+a1x^b1..." No spaces are allowed. The program will detect invalid input and throw a runtime exception.

Private int size(Polynom_able p1):
This function gets polynom_able and return the amount of monoms in the polynom.

Author: Sagi Cohen.
