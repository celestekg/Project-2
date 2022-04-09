# Project-2: This program plays a guessing game with the user. The program prompts the user to guess a value from 1-100, and then tells the user if the value is too high or too low until the user enters the correct value, and prints the result.

![image](https://user-images.githubusercontent.com/56613527/162595158-93a2245d-5733-4a00-af90-15f56b8de578.png)

#include <iostream>
#include <cstdlib>
#include <string>
#include <ctime>

using namespace std;

int main()
{
	srand(time_t(NULL));

	int count;
	int random;
	int guess;
	char response;

	do
	{
		count = 0;
		random = rand() % 100 + 1;

		do
		{
			cout << "Guess a number between 1-100: ";
			cin >> guess;

			count++;

			if (guess == -1)
				break;
			else if (guess < 1 || guess > 100)
				cout << guess << " is out of range." << endl;
			else if (guess > random)
				cout << guess << " is too high, try again." << endl;
			else if (guess < random)
				cout << guess << " is too low, try again." << endl;
		} while (guess != random);

		if (guess == -1)
		{
			count--;
			cout << "You have exited from the game." << endl;
			cout << "Number of guesses: " << count << endl;
		}
		else
		{
			cout << "Congratulations! You guessed the number correctly in " << count << " attempts." << endl;
		}

		cout << "\nDo you want to play again? (Y/N): ";
		cin >> response;

	} while (response == 'Y' || response == 'y');

	cout << "Thank you for playing! " << endl;

	cout << endl;
	return 0;
}
