# Math

## Algorithm to calculate Arithmetic and Geometric progression
### https://repl.it/@O_Slape/Progression-maths 
#### '#include <iostream>'
#### '#include <cstdlib>'
#### '#include <ctime>'
#### 'using namespace std;'
#### 'int main () {'
#### &nbsp; 'int a, count, arit, geo = 1;'
#### &nbsp; 'cout << "Please insert a number: \n";'
#### &nbsp; 'cin >> a;'
#### &nbsp; 'for( count=0; count<10; count++ ){'
#### &nbsp; &nbsp; 'arit += a;'
#### &nbsp; &nbsp; 'geo *= a;'
#### &nbsp; '}'
#### &nbsp; 'cout << "\n" << "Arithmetic progression: " << arit << "\n";'
#### &nbsp; 'cout << "Geometric progression: " << geo;'
#### '}'

'''C++
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
'''
