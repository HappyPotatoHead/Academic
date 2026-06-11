---
aliases:
  - September 2021
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
```cpp
cout << x << " + " << y << " = " << x + y;
cout << x << " - " << y << " = " << x - y;
cout << x << " * " << y << " = " << static_cast<int>(x * y);
cout << x << " / " << y << " = " << fixed << setprecision(3) << x / y;
```
### Question b
```cpp
#include <iostream>
#include <cmath>

using namespace std;

int main(){
	double c, temp, x, b,a;
	cout << "a: ";
	cin >> a;
	cout << "b: ";
	cin >> b;
	cout << "x: ";
	cin >> x;
	temp = a * (pow(x,2)/(b+x));
	c = pow(temp, 1/2);
	cout << "The value of c is " << c << endl;
	return 0;
}
```
### Question c
```cpp
#include <iostream>
#include <string>

using namespace std;

int main(){
	// compute the total consonants and vowels of a name
	// provide an output with the name as shown
	string name = "Jimmy Ding Jia Kang";
	int vowel_a=0, vowel_e=0, vowel_i=0, vowel_o=0, vowel_u=0;
	int consonant=0;
	for(int i =0; i < name.length(); i++){
		if(toupper(name[i]) == 'A')
			vowel_a++;
		else if(toupper(name[i]) == 'E')
			vowel_e++;
		else if(toupper(name[i]) == 'I')
			vowel_i++;
		else if(toupper(name[i]) == 'O')
			vowel_o++;
		else if(toupper(name[i]) == 'U')
			vowel_u++;
		else 
			consonant++;
	}
	cout << "Name: " << name;
	cout << "a: " << vowel_a;
	cout << "e: " << vowel_e;
	cout << "i: " << vowel_i;
	cout << "o: " << vowel_o;
	cout << "u: " << vowel_u;
	cout << "Consonant: "<< consonant;
	return 0;
}
```
## Question 2
### Question a
#### (i) a = 40, b = 12, c = 21
```cpp
if((c % 8-9 <= b/c) || a < c && !(c > --b)))
if( (0 <= 0) || 39 < 21 && !(21 > 11)))
true || false && false
true || false
--> true
```
#### (ii) a = 40, b = 12, c = 21
```cpp
if (!(--c - 19) || (b++ > a-- % 2))
!(20-19) || (12 > 40 % 2)
!(1) || 12> 0
false || true
--> true
```
#### (iii) a = 40, b = 12, c = 21
```cpp
if(!(b-- == 11) || 0 < a-- % c++))
!(12 == 11) || 0 < 40 % 21
!(false) || false
true || false
--> true
```
### Question b
#### (i) x = 5, y = 1
```cpp
#include <iostream>
using namespace std;
int main(){
	int x,y,z =8;
	cout << "Please enter value x and y: " << endl;
	// x = 5, y = 1
	cin >> x >> y;
	// z = 2, x = 6, y = 3
	z /= (x++ - ++y); 
	if (X == 6){
		if (z == 2){
			cout << --z << "\n";
			cout << ++z << endl;
		}
	}
	else {
		cout << z-- << endl;
		cout << z++ << endl;
	}
	return 0;
}
```
#### (i) x =5, y = 1
```cpp
#include <iostream>
using namespace std;
int main(){
	int x,y,z =8;
	cout << "Please enter value x and y: " << endl;
	// x = 5, y = 1
	cin >> x >> y;
	// z = 2, x = 6, y = 3
	z /= (x++ - ++y); 
	if (X == 6){
		if (z == 2){
			cout << --z << "\n";
			cout << ++z << endl;
		}
	}
	else {
		cout << z-- << endl;
	}
	cout << z++ << endl;
	return 0;
}
```
### Question c
```
```
## Question 2

### Question a
#### (i) $a = 40$ and $b = 12$ and $c= 21$ 
```cpp
if((c % 8-9 <= b/c)||(a < c && !(c > --b)))
21 % 8 - 9 <= 12/21 || 40 < 21 && !(21 > 11)
5 - 9 <= 0 || false && false
- 4 <= 0 || false
true || false
----> true
```
**Coding to prove**
```cpp
#include <iostream>
int main() {

	int a{ 39 };
	int b{ 13 };
	int c{ 7 };
	c *= ++a / b--;
	if (c % 8 - 9 <= b / c || (a < c && !(c > --b))){
		std::cout << "TRUEEEEEEEEEEEEEE\n";
	}
	else{
		std::cout << "FALSE\n";
	}
	system("pause");
	return 0;
}
```
#### (ii) $a = 40$ and $b = 12$ and $c= 21$ 
```cpp
if(!(--c - 19) || (b++ > a-- %2))
!(20 - 19) || 12 > 40 % 2
false/*or 0*/ || 12 > 0
false || true 
----> true
```
**Coding to prove**
```cpp
#include <iostream>
int main() {

	int a{ 39 };
	int b{ 13 };
	int c{ 7 };
	c *= ++a / b--;
	if (!(--c - 19)||(b++ > a-- %2)){
		std::cout << "TRUEEEEEEEEEEEEEE\n";
	}
	else{
		std::cout << "FALSE\n";
	}
	system("pause");
	return 0;
}
```
#### (iii) $a = 40$ and $b = 12$ and $c= 21$ 
```cpp
if(!(b-- == 11 || 0 < a-- % c++))
!(12 == 11 || 0 < 40 % 21)
!(false || false)
!(false)
----> true
```
**Coding to prove**
```cpp
#include <iostream>
int main() {

	int a{ 39 };
	int b{ 13 };
	int c{ 7 };
	c *= ++a / b--;
	if (!(b-- == 11 || a-- % c++)){
		std::cout << "TRUEEEEEEEEEEEEEE\n";
	}
	else{
		std::cout << "FALSE\n";
	}
	system("pause");
	return 0;
}
```
### Question b
#### (i)
```cpp
#include <iostream>
int main(){
	int x,y,z = 8;
	std::cout << "Please enter value x and y: " << std::endl;
	std::cin >> x >> y;
	z /= (x++ - ++y);
	// z = z / (5 - 2)
	if(x==6){
		if(z == 2){
			std::cout << --z << '\n';
			std::cout << ++z << '\n';
		}
		else{
			std::cout << z-- << std::endl;
			std::cout << z++ << std::endl;
		}
	}
	return 0;
}
```

#### (ii)
```cpp
#include <iostream>
int main(){
	int x,y,z = 8;
	std::cout << "Please enter value x and y: "<< std::endl;
	std::cin >> x >> y >> z;
	z /= (x++ - ++y);
	if (x == 6){
		if(z==2){
			std::cout << --z <<'\n';
			std::cout << ++z << '\n';
		}
		else{
			std::cout << z-- << std::endl;
		}
		// std::cout << z++ << std::endl;
	}
	std::cout << z++ << std::endl;
	return 0;
}
```

### Question c
```cpp
#include <iostream>
#include <iomanip>
#include <cctype>

int main() {
	int choice{};
	int quantity{};
	char goAgain{};
	double price{};
	double total_price{ 0 };
	int service{};
	double charge{};
	std::cout << std::fixed;
	do {
		std::cout << "Food Menu: \n";
		std::cout << "1. Saba Teriyaki \n2. Salmon Avocado Carpaccio \n3. Unagi Kabayaki \n4. Ebi Katsu Curry\n";
		std::cout << "Pick a choice from the list: \n";
		std::cin >> choice;
		std::cout << "Please enter the quantity that you want: ";
		std::cin >> quantity;
		switch (choice) {
		case 1:
			price = 11.55 * quantity;
			total_price += price;
			std::cout << "You ordered " << quantity << " set(s) of Saba Teriyaki. Price = " << std::setprecision(2) << price << '\n';
			break;
		case 2:
			price = 15.79 * quantity;
			total_price += price;
			std::cout << "You ordered " << quantity << " set(s) of Salmon Avocado Carpaccio. Price = " << std::setprecision(2) << price << '\n';
			break;
		case 3:
			price = 27.45 * quantity;
			total_price += price;
			std::cout << "You ordered " << quantity << " set(s) of Unagi Kabayaki. Price = " << std::setprecision(2) << price<<'\n';
			break;
		case 4:
			price = 15.79 * quantity;
			total_price += price;
			std::cout << "You ordered " << quantity << " set(s) of Ebi Katsu Curry. Price = " << std::setprecision(2) << price<<'\n';
			break;
		default:
			std::cout << "Please choose the available choices.\n";
			continue;
		}
		std::cout << "Do you want to add other food? (Y-Yes, N- No): ";
		std::cin >> goAgain;
	} while (std::toupper(goAgain) != 'N');

	std::cout << "Please choose delivery service: \n";
	std::cout << "1. GrabFood\n2. Foodpanda\n3. DeliverEat\n";
	std::cin >> service;
	switch (service) {
		case 1:
			charge = 5;
			break;
		case 2:
			if (total_price < 25)
				charge = 5;
			break;
		case 3:
			charge += 3 + 0.1 * total_price;
			break;
	}
	std::cout << "Total Food Price: RM" << std::setprecision(2) << total_price<< '\n';
	std::cout << "Delivery Charge: RM" << std::setprecision(2) << charge<< '\n';
	std::cout << "Total price is RM" << std::setprecision(2) << total_price + charge<< '\n';
	system("pause");
	return 0;
}
```

## Question 3
### Question a
```cpp
#include <iostream>
#include <fstream>
#include <iomanip>

using namespace std;

void keyInDoses(int oneDose[], int fullVaccine[], int date[], const int sizeOfArray);
void highestOneDoseVaccination(int oneDose[], int date[], const int sizeOfArray);
void printReport(int fullVaccine[], int oneDose[], int date[], sizeOfArray);

int main(){
	const int SIZE = 6;
	int one_dose[size];
	int full_sode[size];

	int date[size] = {5, 11, 15, 20, 25, 30};

	keyInDoses(oneDose, fullVaccine, date, sizeOfArray);
	highestOneDoseVaccination(oneDose, date, sizeOfArray);
	printReport(fullVaccine, oneDose, date, sizeOfArray);
	
	return 0;
}

void keyInDoses(int oneDose[], int fullVaccine[], int date[], const int sizeOfArray){
	// key in accumulated total doses in sequence into the array
	// into both array of at least 1 dose and fully vaccinated
	cout << "Please key in the accumulated doses.\n";
	for(int i = 0; i < sizeOfArray; i++){
		cout << "Date: " << date[i] << " - MAY - 2021\n";
		cout << "At least 1 dose : ";
		cin >> oneDose[i];
		cout << "Fully Vaccinated: "
		cin >> fullVaccine[i];  
	}	
}
void highestOneDoseVaccination(int oneDose[], int date[], const int sizeOfArray){
	// obtain the highest number of doses injected for at least 1 dose on a particular date range in May 2021
	// The date is determined by user
	// find average doses per day
	int total = 0, count = 0;
	int start_date, end_date, start_index, end_index;
	int highest = oneDose[0];
	cout << "Start date: ";
	cin >> start_date;
	cout << "End date: ";
	cin >> end_date;
	for(int i =0; i < sizeOfArray; i++){
		if(date[i] == start_date){
			start_index = i;
		}
		else if(date[i] == end_date){
			end_index = i;
		}
	}
	for(int i = start_index; i <= end_index; i++){
		if(oneDose[i] > highest){
			highest = oneDose[i];
		}
		total+=oneDose[i];
		count++;
	}
	cout << highest << " doses are given from " << date[start_index] << " of May 2021 till "<< date[end_index] << " of May 2021\n";
	cout << "(" << fixed <<setprecision(2)<< static_cast<double>(total)/count << " doses in average per day).\n";
	cout << "It is the highest number of at least 1 dose given within that period in Mayt."
}
void printReport(int fullVaccine[], int oneDose[], int date[], sizeOfArray){
	ofstream writeFile("MAY 2021.txt");
		writeFile << "MALAYSIANS WHO RECEIVED COVID-19 VACCINE\NMAY 2021 REPORT\NTotal population in MAlaysia: 31.5M";
		for(int i =0; i < sizeOfArray; i++){
			writeFile << "Date: " << date[i] << " - MAY - 2021\n";
			writeFile << "At least 1 dose: " << oneDose[i] << " ( " << fixed << setprecision(1) << (static_cast<double>(oneDose[i])/31.5e6) * 100 << " ) \n";
			writeFile << "Fully Vaccinated: " << fullVaccine[i] << fixed << setprecision(1) << (static_cast<double>(fullVaccine[i])/31.9e6) * 100 << " ) \n"; 
		}
	
}
```

# Section B
## Question 4
```cpp
#include <iostream>
#include <fstream>
#include <string>

struct Durian {
	std::string type;
	char taste[100];
	int source;
};

void writeDurianDetails(Durian durian[], int& noDurian);
void readDurianDetails(Durian durian[], int& noDurian);

int main() {
	int noDurian = 0;
	Durian durian[12];
	writeDurianDetails(durian, noDurian);
	return 0;
}

void writeDurianDetails(Durian durian[], int& noDurian) {
	// Stores the information of user's input into the struct array
	// Writes the information into a text file named durianDetails.txt
	// There are only threee sources:
	/*
	1. Penang
	2. Pahang
	3. Johor
	*/
	char cont;
	std::ofstream writeFile("durianDetails.txt");
	do {
		std::cout << "Type: ";
		std::cin >> durian[noDurian].type;
		std::cout << "Taste: ";
		std::cin >> durian[noDurian].taste;
		std::cout << "Source: ";
		std::cin >> durian[noDurian].source;
		noDurian++;
		std::cout << "Do you want to add more?\n";
		std::cin >> cont;
	} while (toupper(cont) == 'Y');

	for (int i = 0; i <= noDurian; i++) {
		writeFile << durian[i].type << std::endl << durian[i].taste << std::endl;
		switch (durian[i].source) {
		case 1:
			writeFile << "Penang\n";
			break;
		case 2:
			writeFile << "Pahang\n";
			break;
		case 3:
			writeFile << "Johot\n";
			break;
		}
	}
}
void readDurianDetails(Durian durian[], int& noDurian) {
	// read information from the text file of durianDetails.txt
	// Display the types of durians with the taste available according to each source based on user's input.
	// Display the total number of type of durians available in the selected source 
	std::string source;
	int noSource;
	int count = 0;
	std::ifstream readFile("durianDetails.txt");
	if (readFile.fail())
		std::cout << "File has failed to open";
	else {
		for (int i = 0; i <= noDurian; i++) {
			readFile >> durian[i].type;
			// Reading character array from text file
			readFile.getline(durian[i].taste,100);
			readFile >> source;
			if (source == "Penang")
				durian[i].source = 1;
			else if (source == "Pahang")
				durian[i].source = 2;
			else
				durian[i].source = 3;
			readFile.ignore();
		}
	}
	std::cout << "Please enter the source to view the available types of durian: ";
	std::cin >> source;
	if (source == "Penang")
		noSource = 1;
	else if (source == "Pahang")
		noSource = 2;
	else
		noSource = 3;
	for (int i = 0; i <= noDurian; i++) {
		if (durian[i].source == noSource) {
			std::cout << "Type[" << i + 1 << "]: " << durian[i].type << std::endl;
			std::cout << "Taste: " << durian[i].taste << std::endl;
			count++;
		}
	}
	std::cout << "There are total of " << count << " type(s) of durian(s) available in " << source << std::endl;
}
```
## Question 5

# Next Paper
[[Past Year Papers/Year 1/Semester 1/Programming/April 2021|April 2021]]