# Math

## Algorithm to calculate Arithmetic and Geometric progression
### https://repl.it/@O_Slape/Progression-maths 

``` C++
#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

int main () {
  
  int a, count, arit, geo = 1;
 
  cout << "Please insert a number: \n";
  cin >> a;
  
  for( count=0; count<10; count++ ){
    arit += a;
    geo *= a;
  }
  cout << "\n" << "Arithmetic progression: " << arit << "\n";
  cout << "Geometric progression: " << geo;
}
```
## Identify simple shapes using Co-Ordinates
### https://repl.it/@O_Slape/Shape-finder-from-Coordinates

``` C++
#include <iostream>
#include <fstream>
#include <cstdlib>
#include <string>
#include <map>
#include <vector>
#include <sstream>

using namespace std;

vector<string> split(string value, char token);

int main() {
  int maxCoords = 4;
  int minCoords = 2;
  string shape[maxCoords - 1]; // [0, 1, 2, 3, 4]
  
  for (int i = 0; i < maxCoords; i++ ) {
    cout << "Please enter next Coordinate (x,y):";
    string o;
    cin >> o;
    shape[i] = o;
    if (i == minCoords) { // i == 3?
      string option;
      cout << "Continue ? (y/N)";
      cin >> option;
      if(option == "Y" || option == "y"){
         continue;
      } else {
        break;
      }
    }
  }
  
  for(int i=0; i < maxCoords; i++){
    cout << shape[i] << endl;
  }
  
  // Do the identify algorith
  // Check if it's a valid shape
  // Check if it's a triangle
  // Check if it's a rectangle/square

  //num [0][0] = split (input, ',').at(0);
  //num [0][0] = split (input, ',').at(1);
  
  //else{
    //cout << "No shape has only 1 Coordinate!";
  //}
  //cout << num[9];
  
  return 0;
}

vector<string> split(string value, char token) {
	stringstream ss(value);
	vector<string> vect;

	while (ss.good()) {
		string substr;
		getline(ss, substr, token);
		vect.push_back(substr);
	}

	return vect;
}
```

## Greatest Common Divisor and Least Common Multiple
### In maths the Greatest Common Divisor (GCD) is the largest positive integer that divides into two or more intergers which are not all 0.
### In maths the Least Common Multiple (LCM) is The least common multiple to appear in a list of multiplications of two or more intergers which are not all 0. 
## Examples
### What is the GCD of 22 and 32 ? 
### The divisors of 22 are 1, 2, 11, 12.
### The divisors of 32 are 1, 2, 4, 8, 16, 32. 
### Both have 1 and 2 in their lists. This means that 2 is the GCD. 
###
### What is the LCM of 6 and 10 ?
### the Multiplications of 6 are 6, 12, 18, 24, 30, 36, 42, ... And so on.
### The Mulitplications of 10 are 10, 20, 30, 40, 50, 60, ... And so on.
### The LCM in these lists is 30, therefore the LCM of 6 and 10 is 30.
