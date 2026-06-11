---
aliases:
  - September 2022
tags:
  - PYQ
  - Programming
Creation Date: 2024-05-22T13:31:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question a
#### (i)
```cpp
cout << x + y << endl; -->  30
cout << y - v << endl; --> 18.4
cout << v * w << endl; --> 21.888
cout << z % static_cast<int>(w) << endl; --> 1
```
#### (ii)
```cpp
#include <iostream>
#include <iomanip>
using namespace std;
int main(){
	int x =2, y = 28, z = 3;
	double v = 9.6, w = 2.28;
	cout << "Welcome to Maths Corner" << endl;
	cout << "(A) " << x << " % " << y << " = " << x % y << endl;
	cout << "(B) " << v << " * " << z << " = " << fixed << setprecision(1) << v * z << endl; 
	cout << "(C) " << y << " - " << w << " + " << z << " = " << fixed << setprecision(1) << y - w + z << endl;
	cout << "(D) " << v << " + " << x << " / " << w << " = " << fixed << setprecision(2) << v + x / w << endl;
	return 0;
}
```
### Question b
```cpp
#include <iostream>
using namespace std;
int main(){
	int integer_1, integer_2;
	cout << "Please key in value 1: ";
	cin >> integer_1;
	cout << "Please key in value 2: ";
	cin >> integer_2;
	
	if(integer_1 > integer_2)
		cout << integer_1 << " is greater than " << integer_2 << endl;
	else if(integer_2 > integer_1)
		cout << integer_2 << " is greater than " << integer_1 << endl;
	else
		cout << integer_1 << " is equal to " << integer_2 << endl;
	return 0;
}
```
## Question 2
### Question a
#### (i) x = 3, y =0, z = 1
```cpp
if((++x > --z) || !y && !z)
((4 > 0) || 1 && 0)
(true || false)
--> true
```
#### (ii) x = 3, y = 0, z = 1
```cpp
if(!y && (--x - ++y - --z) && (z < 3))
(!0 && ( 2 - 1 - 0) && (1<3))
(1 && (1) && (true))
--> true
```
### Question b
```cpp
#include <iostream>
using namespace std;

int main(){
	int y, x, z = 40;
	cout << "Please enter value x & y: " << endl;
	cin >> x >> y;
	z *= (x++ - --y);
	if (y == 4){
		if (c == 7)
			cout << z-- << "\n";
		else
			cout << z << endl;
	}
	cout << --z << endl;
	cout << z-- + ++y << endl;
	
	return 0;
}
```
#### (i) x = 7 and y = 4 z = 40
```cpp
z = z * (x++ - --y)
  = 40 * (7 - 3)
  = 40 * 4
  = 160
x = 8, y = 3, z = 160
// Output is here
159
163
```
#### (ii) x = 6, y = 5, z = 40
```cpp
z = z * (x++ - --y)
  = 40 * (6 - 4)
  = 40 * 2
  = 80
x = 7, y = 4, z = 80
// output is here
80 // z is 79 now
78
83
```
### Question c
```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main(){
	// read a character from user and validate whether the input is an alphabet or not
	char alpha;
	char cont;
	do{
		cout << "Enter an alphabet: ";
		cin >> alpha;
		if(isalpha(alpha) == false)
			cout << "\""<< alpha << "\"" << " is not an alphabet" << endl;
		else{
			if(toupper(alpha) == 'A' || toupper(alpha) == 'E' || toupper(alpha) == 'I' || toupper(alpha) == 'O' || toupper(alpha) == 'U')
				cout << "\"" << alpha << "\"" << " is a VOWEL" << endl;
			else
				cout << "\"" << alpha << "\"" << " is a CONSONANT" << endl;
		}
		cout << "Do you wish to continue? " << endl;
		cin >> cont;
	}while(toupper(cont) == 'Y');
	return 0;
}
```
## Question 3
### Question a
#### (i)
```cpp
void getInput(double &a, double &b, double &c);
double caclulateDiscrminant(double a, double b, double c);
void determineRoots(double discriminant, double a, double b, double c);
```
#### (ii)
```cpp
void getInput(double &a, double &b, double &c){
	// read a, b and c from the user and refer them to main function
	cout << "Please key in the value a, b and c: ";
	cin >> a >> b >> c;
}
```
#### (iii)
```cpp
double calculateDiscriminant(double a, double b, double c){
	// calculate the discrinant value and return it to main function
	return (pow(b,2) - 4(a)(c))
}
```
#### (iv)
```cpp
void determineRoots(double discriminant, double a, double b, double c){
	// Calculate the roots based on the conditions mentioned aboce using the discriminant and display the values
	double root_a, root_b;
	cout << fixed << setprecision(1);
	
	if (discriminant == 0)
		cout << "There are no real roots" << endl;
	else if (discriminant > 0){
		root_a = (-b + pow(discriminant, 1/2) ) / 2a;
		root_b = (-b - pow(discriminant, 1/2) ) / 2a;
		cout << "The roots of x are " << root_a << " and " << root_b <<"."<< endl;
	else{
		root_a = (-b + pow(discriminant, 1/2) ) / 2a;
		cout << "The root of x is " << root_a << "."<<endl;
	}  
}
```
#### (iv)
```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main(){
	double a, b,c;
	double discriminant;
	getInput(a,b,c);
	discriminant = calculateDiscriminant(a,b,c);
	determineRoots(discriminant, a, b, c );
	return 0;
}
```

### Question b
```cpp
void readInputToArray(string filename, int storeFigure[], int &totalFigure){
	// reads integers from a text file 
	// store in one dimensional array known as storeFigure
	ifstream readFile(filename);
	if (readFile.fail())
		cout << "File has failed to open." << endl;
	else{
		while(!readFile.eof()){
			// assuming totalFigure starts with 0
			readFile >> storeFigure[totalFigure];
			readFile.ignore();
			totalFigure++;
		}
	}
}
```
# Section B
## Question 4
### Question a
#### (i)
```cpp
struct fruitData{
	string fruitName;
	float price;
};
```
#### (ii)
```cpp
fruitData fruits[20];
```
#### (iii)
```cpp
struct invoiceData{
	int NoOfFruitItem_ordered;
	float pound_ordered;
	float totalFruitprice;
	// This is to store the fruit that has been bought
	fruitData fruit[20];
};
```
#### (iv)
```cpp
invoiceData customers[100];
```
### Question b
```cpp
void readInput(fruitData fruits[]){
	// reads the text file "fruit.txt"
	// stores the information into the fruitData using struct array
	// total number of fruits is stored in global variable = item
	ifstream readFile("fruit.txt")
	if(readFile.fail())
		cout << "File has failed to open" << endl;
	else{
		while(readFile.eof()){
			// assuming item is 0
			getline(readFile, fruits[item].fruitNAme);
			readFile >> price;
			readFile.ignore();
			// item is universal
			item++;
		}
	}
}
```
### Question c
```cpp
void fruitPurchas(invoiceData customers[]){
	// allows user to purchaes fruits by key in the fruit name and the weight of each fruit in pounds.
	// display and store the ouput to "customersHistory.txt"
	ofstream writeFile("customersHistory.txt");
	string name;
	double pound;
	char cont;
	string next_purchase;
	int customer_id = 0;
	int fruit_id = 0;
	do{
		writeFile << "Customer ID: " << customer_id + 1;
		customers[customer_id].NoOfFruitItem_ordered = 0;
		customers[customer_id].totalFruitprice = 0;
		do{
			cout << "Enter the fruit name that customer would like to purchase: " << endl;
			cin >> name;
			cout << "How many pounds? "<< endl;
			cin >> pound;
			customers[customer_id].fruit[fruit_id].fruitname = name;
			customers[customer_id].pound_ordered = pound;
			if(name == "Banana"){
				customers[customer_id].fruit[fruit_id].price = pound * 1;
			}
			else if(name == "Apple"){
				customers[customer_id].fruit[fruit_id].price = pound * 2;
			}
			else if(name == "Pear"){
				customers[customer_id].fruit[fruit_id].price = pound * 2.5;
			}
			else if(name == "Orange"){
				customers[customer_id].fruit[fruit_id].price = pound * 1.5;
			}
			else if(name == "Papaya"){
				customers[customer_id].fruit[fruit_id].price = pound * 1.4;
			}
			writeFile << "Fruit type: " << name << endl;
			writeFile << "No. of pound: " << customers[customer_id].pound_ordered;
			customers[customer_id].NoOfFruitItem_ordered++;
			customers[customer_id].totalFruitprice += customers[customer_id].fruit[fruit_id].price;
			cout << "Do you wish to add other fruits? " << endl;
			cin >> cont;
			if(toupper(cont) == 'Y')
				fruit_id++;
				
		}while(toupper(cont) == 'Y');
		 
		cout << "You have ordered " << customers[customer_id].NoOfFruitItem_ordered << " item(s) with total price of RM " << customers[customer_id].totalFruitprice << ". " << endl;
		
		writeFile << "Customer " << customer_id + 1 << " have ordered " << customers[customer_id].NoOfFruitItem_ordered << " item(s) with total price of RM " << customers[customer_id].totalFruitprice << ". " << endl;

		cout << "Next Purchase? "<< endl;
		cin >> next_purchase;
		if(next_purchase == "Yes")
			customer_id++;
			
	}while(next_purchase == "Yes");
	
	writeFile.close();
}
```
## Question 5
### Question a
```cpp
struct PUBG{
	string username_of_PUBG;
	int total_games_played;
	double hours_games_played;
	bool current_online_status;
}
```
### Question b
#### (i)
```cpp
void readUser(PUBG PUBGAcc[], int &totalPlayer){
	// input is done here
	// store the information of multiple users (key in by user) into PUBG using struct array
	// update the total number of players -> assuming it is 0
	cout << "Username: ";
	cin >> PUBGAcc[totalPlayer].username_of_PUBG;
	cout << "Total Games Played: ";
	cin >> PUBGAcc[totalPlayer].total_games_played;
	cout << "Hour'ss games played: ";
	cin >> PUBGAcc[totalPlayer].hours_games_played;
	cout << "Current online status: ";
	cin >> PUBGAcc[totalPlayer].current_online_status;
	
	totalPlayer++;
}
```
#### (ii)
```cpp
int totalGamesPlayedAllUser(PUBG PUBGAcc[], int totalPlayer){
	// calculates the total games played by all the users
	int total_games =0;
	for(int i =0; i < totalPlayer; i++){
		total_games += PUBGAcc[i].total_games_played;
	}
	return total_games;
}
```
#### (iii)
```cpp
void checkCurrentOnlineStatus(PUBG PUBGAcc[], int totalPlayer){
	// determines the players with the current status show online. The function also calculates the total current online players and displays the output
	int count = 0;
	cout << "Current online player: " << endl;
	
	for(int i = 0; i < totalPlayer; i++){
		if(PUBGAcc[i].current_online_status == true){
			cout << PUBGAcc[i].username_of_PUBG << endl;
			count++;
		}
	}
	cout << "Total of current online player is " << count <<". \n";
}
```
# Next Paper
[[Past Year Papers/Year 1/Semester 1/Programming/September 2021|September 2021]]