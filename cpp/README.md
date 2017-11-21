# C++ Summary Note

### - THE ESSENTIALS -
#### Compile
To compile `test.cpp` in Linux terminal:
`g++ test.cpp -o test`

#### Main function
Every C++ program must have a main function:
```c++
int main() {
  return 0;
}
```

#### Data types
data type | meaning
----: | :----
`int` | integer
`float` | fractional number with 7 digits of precision
`double` | fractional number with 16 digits of precision


#### Libraries
```c++
#include <iostream>
#include <cmath>
```


### - BUILDING BLOCKS -
#### Declare & Initialise
```c++
int a; // declare variable a as integer
a = 1; // initialise a with value 1
```
We can do that in a single line:
```c++
int a = 1;
```

#### If, else if, else
```c++
if ([condition]) {
  [statements]
} else if ([condition]) {
  [statements]
} else {
  [statements]
}
```

#### For loops
```c++
for ([initial]; [condition]; [iteration]) {
  [statements]
}
```
In statements: <br>
`break` : exit the loop. <br>
`continue` : move to next iteration

#### While loops
```c++
while ([condition]) {
  [statements]
}
```

#### Write to file Streams
```c++
#include <fstream>
int main() {
  std::ofstream file;
  file.open("somefile.txt");
  if (!file) return 1;
  file << "Some text to put in file.txt";
  file.close();
  return 0;
}
```
`file.width(10)` : columnate, set column width <br>
`file.precision(5)` : set precision

#### Standard Input Output
```c++
#include <iostream>
int main() {
  int a;
  std::cout << "Enter an integer: ";
  std::cin >> a;
  std::cout << "Your integer is " << a << std::endl;
  return 0;
}
```
<br>
#### Vectors

```c++
#include <vector>
int main() {
  std::vector<double> myVector(10, 3.14);
}
```
This creates `myVector` with `10` elements (of type `double`), each initialised to `3.14`.

`myVector[0]` : `3.14`, the first element of `myVector` <br>
`myVector.size()` : `10`, the number of elements of `myVector` <br>
`myVector.resize(15)` : set the number of elements to `15` <br>
`myVector.push_back(3)` : append new element `3` to `myVecor` <br>

#### Strings
```c++
#include <string>
int main() {
  std::string myString("abc");
}
```
`myString[0]` : `a`, the first character of `myString` <br>
`myString.size()` : `3`, the length of `myString`

### - MEMORY -
All variables are stored in memory, each occupies a separate location in RAM. <br>
Addresses are displayed in hexadecimal: `0x7ffdc82c655c` <br>
```c++
int a = 1;
&a; // evaluates to 0x7ffdc82c655c
int *pa = &a; // declare a pointer pa to integer
              // initialise pa with 0x7ffdc82c655c
pa; // evaluates to 0x7ffdc82c655c
*pa; // evaluates to 1
```
`&` : address-of operator <br>
`*` : declare pointer when declaring, otherwise value-at operator

### - FUNCTION -
```c++
[returnType] [functionName]([parameters]) {
  [functionBody]
}
```
parameters are separated with commas `,` <br>

#### Function overloading
```c++
#include <cmath> // just for std::exp and std::log
double pow(double a, int b) { // notice b is integer
  double r = 1;
  for (int i = 0; i < b; i++) { r = r*a; }
  return r;
}
double pow(double a, double b) { // notice b is double
  return std::exp(b * std::log(a));
}
```
`pow(3, 2)` evaluates to `9` using the __first__ `pow` function. <br>
`pow(9, 0.5)` evaluates to `3` using the __second__ `pow` function. <br>

#### Default argument value
```c++
#include <cmath> // just for std::log
double logn(double a, double b=10.0) {
  return std::log(a)/std::log(b);
}
```
`logn(5.5, 2.1)` evaluates to log of `5.5` base `2.1` <br>
`logn(5.5)` evaluates to log of `5.5` base `10` <br>

#### Passing arguments by value
```c++
int plusOne(int a) {
  a = a + 1;
  return a;
}
main() {
  int b = 3;
  plusOne(b); // evaluates to 4
  b; // evaluates to 3
  plusOne(6); // evaluate to 7
}
```
Calling `plusOne(b)` creates a copy of `b`, modifies the copy, and destroys the copy when `plusOne` returns.

Calling `plusOne(b)` does __not__ modify `b`.

#### Passing arguments by reference
```c++
int plusOne(int &a) { // notice the &
  a = a + 1;
  return a;
}
main() {
  int b = 3;
  plusOne(b); // evaluates to 4
  b; // evaluates to 4
  plusOne(6); // error, cannot modify 6
}
```
Unlike passing by value, calling `plusOne(b)` here does __not__ create a copy of `b`, so the modification applies to `b` itself.

#### Passing arguments by constant reference
```c++
int plusOne(const int &a) { // notice const and &
  return a + 1; // no modification for a
}
main() {
  int b = 3;
  plusOne(b); // evaluates to 4
  b; // evaluates to 3
  plusOne(6); // evaluates to 7
}
```
Calling `plusOne(b)` does not modify `b`, nor does it create a copy of `b`.

  <span></span> | copy `b` | does not copy `b`
 -: | -------: | -------:
 __modify `b`__ |  | by reference
 __does not modify `b`__ | by value | by constant reference

### - CLASS -
```c++
class fruit {
public:
  fruit(double p, int q) : price(p), quantity(q) {};
  double totalPrice() {
    return price * quantity;
  }
protected:
  double price;
  int quantity;
};
```
`fruit myFruit(3.0, 5)` creates an instance of `fruit` with price `3.0` and quantity `5`.

Then `myFruit.totalPrice()` evaluates to `15.0`

#### Inherit
One class (`apple`) can inherit from another class (`fruit`)
```c++
class apple : public fruit {
public:
  apple(int q) : fruit(2.5, q) {};
};
```

#### Virtual functions
Let's say we were to define the following member function in `apple`:
```c++
std::string location() {
  return "Aisle: 5, Location: 12";
}
```
In order to access `location()` from the base class `fruit`, we need a virtual function in `fruit`.

Virtual function in `fruit`:
```c++
virtual double profit() { return -1; }
```
Pure virtual function in `fruit`:
```c++
virtual double profit() = 0;
```
Once we've defined a virtual function in `fruit`, we can access `location()` in `main()`:
```c++
apple a(5);
fruit *pa = &a;
(*pa).location(); // evaluates to "Aisle: 5, Location: 12"
```
alternatively, we can use `*pa->location();` instead of `(*pa).location();`.

#### Operator overloading
We can make operators do different things for variables with different data types.
```c++
class myClass {
  double operator[](int i) {
    return ...;
  }
};
```
#### Template
Sometimes our functions can work on several data types. <br>
We can use template to define the function just once for all types, instead of defining one for each data type.
```c++
template <typename T>
```
then we can use `T` in place of the data type.
