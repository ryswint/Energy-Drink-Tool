//Ryan Swint
//Fall 2021 Chapter 1
//Module 2

//Energy Drink Preparation Program
//This program calculates how many energy drinks are needed throughout the gaming week


#include <iostream>
#include <math.h> //Included for "ceil" rounding function
using namespace std;

//===================Variables & Constants=============================================================//

const int MinPerHour = 60.00;

enum week { Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday };

float totalTime;
float hours;
float partialCans;
float partialPacks;

char answer;
char answerCap;

int perHour;
int minutes;
int fourPacks;
int cans;
int cansArray[7];
int days = 7;
int minutesArray[7];

string name;
string weekArray[7] = { "Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday" };

bool answerLoop = 1;
bool packs;
bool shortTime;

//===================Main Function=====================================================================//

int main()
{

	cout << "*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*\n";
	cout << "*=*=*=*=*=*=*=*=*=[EDPP]*=*=*=*=*=*=*=*=*=*=*=*\n";
	cout << "*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*=*\n\n";

	cout << "Welcome to the Energy Drink Preparation Program!\n\n";
	cout << "What is your Name? ";
	cin >> name; //Name Input
	cout << "Hello " << name << ", it is nice to meet you!\n\n";


	cout << "How many Energy Drinks do you drink per hour? ";
	cin >> perHour; //Energy Drinks per hour input

	if (perHour == 0)
	{
		cout << "Why are you even using this program " << name << "?";
		return 0; //END PROGRAM
	}
	else if (perHour > 2)
	{
		cout << perHour << " Energy Drinks per hour?  Your poor heart!\n";

	}
	else
	{
		cout << "Awesome! " << perHour << " Energy Drinks per hour!\n";
	}

	for (int i = Sunday; i <= Saturday; i++) //Minutes per day input
	{
		cout << endl << "For how many Minutes will you be playing on " << weekArray[i] << "? ";
		cin >> minutesArray[i];

		if (minutesArray[i] == 0)
		{
			cout << name << ", you need to make better life choices!\n";
		}
		else if (minutesArray[i] > 240)
		{
			cout << "That's some serious game time!\n";

		}
		else if (minutesArray[i] < 60)
		{
			cout << "Those are rookie numbers, you gotta get those up!\n";
		}



	}

	for (int i = 0; i < 7; i++) //Calculate total game time
	{
		minutes += minutesArray[i];
	}
	totalTime = minutes / 60.0f;
	hours = minutes / MinPerHour;
	minutes %= MinPerHour;

	cout << endl << "That puts your game week at " << totalTime << " hours, or " << hours << " hours and " << minutes << " minutes!\n";

	while (answerLoop) //Decision to give answer in terms of 4-packs
	{
		cout << endl << "Do you want to keep the result in number of 4-packs needed? (y/n) ";
		cin >> answer;
		answerCap = toupper(answer);
		switch (answerCap)
		{
		case 'Y':
			packs = true;
			answerLoop = false;
			break;
		case 'N':
			packs = false;
			answerLoop = false;
			break;
		default:
			cout << endl << "What do you mean " << answer << "? The instructions were not that hard " << name << "! Have an Energy Drink and try again!";
			answerLoop = true;
		}

	}
	answerLoop = true;

	while (answerLoop) //Decision to include energy drinks for sessions less than an hour
	{
		cout << endl << "Do you want an Energy drink when playing less than an hour (y/n) ";
		cin >> answer;
		answerCap = toupper(answer);
		switch (answerCap)
		{
		case 'Y':
			shortTime = true;
			answerLoop = false;
			break;
		case 'N':
			shortTime = false;
			answerLoop = false;
			break;
		default:
			cout << endl << "What do you mean " << answer << "? The instructions were not that hard " << name << "! Have an Energy Drink and try again!";
			answerLoop = true;
		}

	}



	for (int i = Sunday; i <= Saturday; i++) //Calculate Cans per day
	{
		hours = minutesArray[i] / MinPerHour;
		minutes = minutesArray[i] % MinPerHour;
		totalTime = minutesArray[i] / 60.0f;

		if (minutesArray[i] < 60 && !shortTime)
		{
			cans = 0;
		}

		else
		{
			partialCans = totalTime * perHour;
			cans = ceil(partialCans);
		}

		if (cans == 0)
		{
			days -= 1;
		}
		cansArray[i] = cans;
		cout << endl << "With a game time of " << hours << " hours and " << minutes << " minutes, you need " << cans << " cans for " << weekArray[i] << ".";
	}

	cans = 0;
	for (int i = 7; i > 0; i--) //Calculate Total Cans
	{
		cans += cansArray[i];
	}

	cout << endl << endl << days << " days require Energy Drinks.";
	cout << endl << "Energy Drinks for the week: " << cans;
	if (packs)
	{
		partialPacks = cans / 4.00f;
		fourPacks = ceil(partialPacks);
		cout << endl << "4-Packs needed for the week: " << fourPacks << endl;
	}

	cout << endl << "Thank You " << name << "! Goodbye!" << endl;
	return 0;//END PROGRAM

}
