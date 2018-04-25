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
### https://repl.it/@O_Slape/Shape-find

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
bool CheckCoordRange(int opt);
bool CheckDiffInput(int count, string o);

bool keepAlive = true;

int maxCoords = 4;
int minCoords = 3;
int Triangle = 3;
int Square = 4;
int count = 0;

int main() {

  string shape[maxCoords]; // [0,1 , 1, 2, 2, 10, 3, 4] 

  
  // Main Loop
  while(keepAlive) {
    // Increment the counter
    count++;
    cout << "Iteration " << count << endl;
    cout << "Please enter Coordinate (x,y):";
    string o;
    cin >> o;
    if(count == 4){
      cout << "This is a Square" << endl;
      keepAlive = false;
    }
    vector<string> input = split(o, ',');
    // Cheeck if input is valid, otherwise output an error and restart
    if (!(CheckCoordRange(std::stoi(input[0])) && CheckCoordRange(std::stoi(input[1])))){ // 0 - 9
      cout << "Incorrect not a Coordinate" << endl;
      count--;
      continue;
    }
    
    // Add the option to the list
    shape[count] = o;
    
    // Check if reached to minimum allowed inputs
    if (count == minCoords) { // i == 3?
      cout << "Continue ? (y/N)";
      cin >> o;
      if(!(o == "Y" || o == "y")){
        //CheckDiffInput(count, o);
        cout << "This is a Triangle" << endl;
        keepAlive = false;
      }
        else{
          continue;
        }
    }
    // Check to see if reached to max coords
    if(count == maxCoords)
       keepAlive = false;
 }
 
  return 0;
}

bool CheckCoordRange(int opt) {
  if (opt >= 0 && opt <= 9){
    return true;
  }
  
  return false;
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
##

## Greatest Common Divisor and Least Common Multiple
### In maths the Greatest Common Divisor (GCD) is the largest positive integer that divides into two or more integers which are not all 0.
### In maths the Least Common Multiple (LCM) is The least common multiple to appear in a list of multiplications of two or more integers which are not all 0. 
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

## Probability.
### Probability is the measure of the likelihood that an event will occur. Probability is quantified in numbers, usually percentages or fractions. 
## Examples. 
### What is the probability of having 7 when rolling two dice? 
### There is 36 different possibilities that can occur. Such as 1,1 1,2 1,3 and so on. There is 6 of these possibilities containing a 7. These are 2,5 3,4 4,3 2,5 6,1 1,6. Probability is generally expressed as a fraction of this format: P(chances/total). Therefore, the probability of having a 7 when rolling two dice is P(6/36). This can be shortened into P(1/6). 
### What is the probability of having at least a 2 when rolling two dice? 
### Well again there is 36 possibilities. 11 of these contain a 2. these are: 1,2 2,1 2,3 3,2 4,2 2,4 5,2 2,5 6,2 2,6 2,2. Therefore the probability of having at least one 2 when rolling two dice is P(11/36). 

## Independent events.
### Independent events dont get effected from events that have happened before. This can also be quantified into probability. We can do this by multiplying the probability of independent single events.   
## Examples.
### What is the probability of rolling a 7 after rolling a 2? 
### The probability for both of these we already know as P(1/6) and P(11/36). Because these two events happen independently we have to multiply the Probabilities of the single events to get the Probability of two independent events. This will be P(1/6) X P(11/36). P(1/6) X P(11/36) = P(11/216). 

## Event from a discrete random variable
### If we want to have a random variable such as an integer there needs to be a standard at which we call random. If we use two integers for this, we can have the random integer and find the probability of it being divisible by 5. For the random integer let’s call it X, we have to decide a range that is acceptable. If we don’t set a range there is an infinite amount of possible numbers that could be X as integers are any whole number positive or negative and we can’t calculate that. Assume A is a very large negative number and B is a very large positive number and this our range. We can randomly assign X between the range of A and B. We know that every 5th number is divisible by 5. So the probability of X/5 is the range of A to B divided by 5. 

## Vectors
### A Vector is a geometric object that has magnitude (Length) and direction.
![Vector]( https://github.com/Oliver-Slape/Math/blob/master/Vector.PNG) 
### Here is an example of how you can use vectors to determine shape paramaters.
### https://www.w3schools.com/code/tryit.asp?filename=FPSL137E5T4F

``` html
<html>
<body>

<canvas id="myCanvas" width="300" height="150" style="border:1px solid #d3d3d3;"></canvas>

<br>
<button onclick="move(1)">LEFT</button>
<button onclick="move(2)">UP</button>
<button onclick="move(3)">DOWN</button>
<button onclick="move(4)">RIGHT</button>
<br>
<button onclick="move(5)">DIAGONAL RIGHT DOWN</button>
<button onclick="move(6)">DIAGONAL RIGHT UP</button>
<br>
<button onclick="move(7)">DIAGONAL LEFT DOWN</button>
<button onclick="move(8)">DIAGONAL LEFT UP</button>
<br>
<button onclick="shape()">SHAPE?</button>


<script>
var c = document.getElementById("myCanvas");
var ctx = c.getContext("2d");
ctx.beginPath();

var curX=parseInt(prompt("Please enter the initial X"));;
var curY=parseInt(prompt("Please enter the initial Y"));;

function move(dir){
var mag = parseInt(prompt("Please enter the magnitude"));

if(dir==1){
  //left
  ctx.moveTo(curX, curY);
  curX = curX-mag;
  ctx.lineTo(curX, curY);  
  alert("Vector Direction: Left / Vector Magnitude: "+mag);
}else if(dir==2){
  //up
  ctx.moveTo(curX, curY);
  curY = curY-mag;
  ctx.lineTo(curX, curY);  
  alert("Vector Direction: Up / Vector Magnitude: "+mag);
}else if(dir==3){
  //down
  ctx.moveTo(curX, curY);
  curY = curY+mag;
  ctx.lineTo(curX, curY);  
  alert("Vector Direction: Down / Vector Magnitude: "+mag);
}else if(dir==4){
  //right
  ctx.moveTo(curX, curY);
  curX = curX+mag;
  ctx.lineTo(curX, curY);  
  alert("Vector Direction: Right / Vector Magnitude: "+mag);
}else if(dir==5){
  //diagonal right down
  ctx.moveTo(curX, curY);
  curX = curX+mag/2;
  curY = curY+mag/2;
  ctx.lineTo(curX, curY);  
  alert("Vector Direction: Diagonal Right Down / Vector Magnitude: "+mag);
}else if(dir==6){
  //diagonal right up
  ctx.moveTo(curX, curY);
  curX = curX+mag/2;
  curY = curY-mag/2;
  ctx.lineTo(curX, curY);  
  alert("Vector Direction: Diagonal Right Up / Vector Magnitude: "+mag);
}else if(dir==7){
  //diagonal left down
  ctx.moveTo(curX, curY);
  curX = curX-mag/2;
  curY = curY+mag/2;
  ctx.lineTo(curX, curY);  
  alert("Vector Direction: Diagonal Left Down / Vector Magnitude: "+mag);
}else if(dir==8){
  //diagonal left up
  ctx.moveTo(curX, curY);
  curX = curX-mag/2;
  curY = curY-mag/2;
  ctx.lineTo(curX, curY);  
  alert("Vector Direction: Diagonal Left Up / Vector Magnitude: "+mag);
}

ctx.stroke();

}

function shape(){
  var shape = prompt("Is this a shape Y/N?");

  if(shape=='Y'){
      prompt("What shape?");
  }else {
      alert("Keep drawing!");
  }
}

</script>

</body>
</html>
```


## Algebraic rate of change.
### Describes the rate at which one quantity is changing with a corresponding quantity.
### For example: Miles per Gallon is calculated by diving the number of miles by the number of gallons used.
### The formula is: 
![Pic]( https://github.com/Oliver-Slape/Math/blob/master/RateofChange.png) 

### Rate of change from 10 to 100
#### '(2*100+3)-(2*10+3)/(100-10)=180/90= 2'





