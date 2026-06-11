---
aliases:
  - April 2021
tags:
  - PYQ
  - Programming
Creation Date: 2024-05-22T13:29:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question a
#### (i)
```cpp
#include <iomanip>
```
#### (ii)
```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main(){
	int a = 100. b = 10, c = 6;
	double d = 5.5, e = 2.5;
	cout << "Welcome to Division Section "<< endl;
	cout << "(i)   Division of a/b = " << a/b << endl;
	cout << "(ii)  Division of a/c = " << a/c << endl;
	cout << "(iii) Division of c/b = " << fixed << setprecision(2) << static_cast<double>(c)/b << endl;
	cout << "(iv)  Division of b/a = " << fixed << setprecision(2) << static_cast<double>(b)/a << endl;
	return 0;
}
```
#### (iii)
```cpp
cout << "The output of b * d * e = " << fixed << setprecision(2) << b * d * e << endl;
cout << "The output of ((b -c) - (d - e)) = " << (b - c) - (d - e) << endl;
```
### Question b
```cpp
#include <iostream>
#include <iomanip>
using namespace std;
int main(){
	int number_a, number_b;
	int operation;
	char sign;
	int answer; 
	
	cout << "Key in two numbers: ";
	cin >> number_a, number_b;
	cout << "1. + \n2. - \n3. * \n4. / \n";
	cout << "Select operator:"
	cin >> operation; 
	if(operation == 1)
		sign = '+';
		answer = number_a + number_b;
	else if(operation == 2)
		sign = '-';
		answer = number_a - number_b;
	else if(operation == 3)
		sign = '*'
		answer = number_a * number_b;
	else{
		if(number_b == 0)
			cout << "Invalid operation! " << endl;
		else
			sign = '/';
			answer = number_a / number_b;
	}
	cout << number_a << " "<< sign << " " << number_b << " = " << answer; << endl;  
	return 0;
}
```
## Question 2
### Question a
#### (i) x = 135, y = 38, z = 126
```cpp
if (z/3 <=y && y < z)
126/3 <= 38 && 38 < 126
42 <= 38 && true
false && true 
false
```
#### (ii) x = 135, y = 38, z = 126
```cpp
if(!(--z - 125) || (--y > x-- % 2))
!(125 - 125) || 37 > 1
true || true 
true
```
#### (iii) x = 135, y = 38, z = 126
```cpp
if(!(y<38 || 0))
!(38 < 38 || 0)
!(false || false)
!(false)
true
```
### Question b
#### (i) 
```cpp
#include <iostream>

using namespace std;

int main(){
	int a,b = 3, c;
	cout << "Please enter value a and c:" << endl;
	cin >> a >> c;
	// a = 5, c = 5
	c %= (++a - b--); 
	// c = 5 % (6 - 3)
	// c = 2
	// a = 6
	// b  = 2
	if (a == 6){
		if(c==2){
			cout << c-- << "\n";
			cout << ++c << endl;
		}
	}
		else{
			cout << --c << endl;
			cout << c++ << endl;
		}
	return 0;
}
```
#### (ii) 
```cpp
#include <iostream>

using namespace std;

int main(){
	int a,b = 3, c;
	cout << "Please enter value a and c:" << endl;
	cin >> a >> c;
	// a = 5, c = 5
	c %= (++a - b--); 
	// c = 5 % (6 - 3)
	// c = 2
	// a = 6
	// b  = 2
	if (a == 6){
		if(c==2){
			cout << c-- << "\n";
			cout << ++c << endl;
		}
	}
		else{
			cout << --c << endl;
			}
	cout << c++ << endl;
	return 0;
}
```
### Question c
```cpp
// calculate the total prices that a customer need to pay.
// a customer might have more than one parcel to deliver
// input validation is not required

#include <iostream>

using namespace std;

int main(){
	int region;
	double weight;
	char cont;
	double total_payment = 0;
	do{
		cout << "Pick your delivery region: " << endl;
		cout << "1. Peninsular Malaysia" << endl;
		cout << "2. East Malaysia" << endl;
		cin >> region;
		cout << "Please key in the weight of the parcel in kg: ";
		cin >> weight; 
		switch(region){
			case 1:
				if(weight <= 1)
					total_payment += 8.5;
				else if(weight > 1 && weight <= 2)
					total_payment += 14.00;
				else if(weight > 2 && weight <= 3)
					total_payment += 24.00;
				else
					total_payment += (ceil(weight -3) * 3) + 24.00;
			case 2:
				if(weight <= 1)
					total_payment += 12.5;
				else if(weight > 1 && weight <= 2)
					total_payment += 20.00;
				else if(weight > 2 && weight <= 3)
					total_payment += 32.00;
				else
					total_payment += (ceil(weight -3) * 3) + 32.00;
		}
		cout << "Do you have another parcel? "<< endl;
		cin >> cont;
	}while(cont == 'y');
	cout << "Total payment: RM " << total_payment << "." << endl;
	return 0;
}
```
## Question 3
### Question a
```cpp
bool checkCharacter(string IC);
int convertYearOfBirth(string IC);
void checkEligibility(string name, int year);
```
### Question b
```cpp
cout << "Name: " << endl;
cin >> name;
cout << "IC No (without hypen): " << endl;
cin >> IC;
```
### Question c
```cpp
bool checkCharacter(string IC){
// check for any non-numeric inputs of the IC
	for(int i =0; i < IC.length(); i++){
		if (!isdigit(IC[i]))
			return 0;
	}
	return 1;
}
```
### Question d
```cpp
int convertYearOfBirth(string IC){
	// extract the year from the IC and return to the main functoin with proper format. 
	string year_full;
	string year_st = IC[0];
	string year_nd = IC[1];
	string year_full = year_st + year_nd;
	if(year >= 23)
		year = "19" + year;
	else
		year = "20" + year;
	return stoi(year);
}
```
### Question e
```cpp
void checkEligibility(string name, int year){
	// check the voting eligibility of a Malaysian using the years obtained from C
	// Assuming the election year is 2023
	cout << name << " is " << year << "years old." << endl;
	if(2023 - year >= 18)
		cout << name << " are eligible to vote!" << endl;
	else
		cout << name << " are not eligible to vote!" << endl;
	
}
```
## Question 4
### Question a
```cpp
struct PaintingService{
	int type_house;
	char full_or_not;
	double price_service;
	Address address;
};
```
### Question b
```cpp
PrintingService PaintingList[100]
```
### Question c
```cpp
void PaintingInfo(PrintingService PaintingList[]){
	// get information about type of house, house address and verification of the house furniture. 
	// Put the informatoin into the struct
	int count =0;
	char cont;
	do{
		cout << "Please key in your house type: 1-Flat 2-Apartment 3-Condominium 4-Single Storey 5-Double Storey" << endl;
		cin >> PaintingList[count].type_house;
		cout << "Please key in your house number: ";
		cin >> PaintingList[count].address.houseNumber;
		cout << "Please key in your street name: ";
		cin >> PaintingList[count].address.streetName;
		cout << "Please key in your postcode: ";
		cin >> PaintingList[count].address.postcode;
		cout << "Please key in your city: ";
		cin >> PaintingList[count].address.city;
		cout << "Please key in your state: ";
		cin >> PaintingList[count].address.state;
		cout << "Is your house full of furniture and needs to be shifted? Y=Yes N=No: ";
		cin >> PaintingList[count].full_or_not;
		cout << "Do you want to key in another painting service info? Y=Yes N=No: ";
		cin >> cont;
		if(toupper(cont) == 'Y')
			count++;
	}while(toupper(cont) == 'Y');
}
```
### Question d
```cpp
void TotalChargedEstimatioin(PaintingService PaintingList[]){
	// calculate the estimated charges of each painting services and also total charges from all painting services. 
	// write the painting services details to the output file of painting.txt 
	int total_charge = 0;
	for(int i =0; i< 100; i++){
		switch(PaintingList[i].type_house){
			case 1:
				PaintingList[i].price_service = 1700;
				break;
			case 2:
				PaintingList[i].price_service = 2000;
				break;
			case 3:
				PaintingList[i].price_service = 2200;
				break;
			case 4:
				PaintingList[i].price_service = 2500;
				break;
			case 5:
				PaintingList[i].price_service = 3300;
				break;
		}
	}
	// Finds if it has extra charges
	for(int l = 0; l < 100;l++){
		if(PaintingList[i].full_not_not == 'Y')
			PaintingList[i].price_service += 250
	}
	// Finding the total estimated charges
	for(int j = 0; j<100;j++){
		total_charge += PaintingList[i].price_service;
	}
	
	ofstream writeFile("painting.txt", ios::app);
	if(writeFile.fail())
		cout << "File does not exist";
	else{
		for(int k =0; k< 100; k++){
			switch(PaintingList[i].type_house){
				case 1:
					writeFile << "Flat" << endl;
					break;
				case 2:
					writeFile << "Apartment" << endl;
					break;
				case 3:
					writeFile << "Condominium" << endl;
					break;
				case 4:
					writeFile << "Single Storey" << endl;
					break;
				case 5:
					writeFile << "Double Stoery" << endl;
					break;
			}
			writeFile << PaintingList[i].address.houseNumber << ", " << PaintingList[i].address.streetName << ", " << PaintingList.address.postcode << ", " << PaintingList[i].city << ", " << PaintingList[i].state <<"." << endl;
			writeFile << "House with furniture: " << PaintingList[i].full_or_not << endl;
			writeFile << "Estimated charges: " << PaintingList[i].price_service << endl;
		}
		writeFile << endl;
		writeFile << "Total estimated charges from painting services is "<< total_charge;
	}
	writeFile.close();
}
```