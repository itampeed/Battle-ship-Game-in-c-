# Battle-ship-Game-in-c-
A simple yet amazing game made in c++ using concept of multi dimensional arrays.
I follows simple battle rules.
Your brigade headquarters found some battle ship in your areas, and it is a war time.
Now you have to find them and Hit them using the guns and torpedos (Imaginary) You have.
Better luck...
Here under is the code for the game...

#include <iostream>
#include <conio.h>
#include <bits/stdc++.h>
using namespace std;

int main()
{
  bool ships[4][4] = {
      {0, 0, 0, 0},
      {0, 0, 0, 0},
      {0, 0, 0, 0},
      {0, 0, 0, 0}};
  int totalships = 0;
  int times = 0;
  if (times == 0)
  {
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
        if (ships[i][j] == 1)
        {
          totalships++;
        }
        else
        {
          continue;
        }
      }
    }
    times++;
  }
  int hits = 0, numberofturns = 0;
  while (totalships > 0)
  {
    cout << "Behold!!\t " << totalships << " enemy ships found in the waters.\n";
    getch();
    cout << "You are now tasked to find them and take them out...!!\n";
    cout << "Over and out\n\n";
    getch();
    int row, column;
    cout << "Choose a row between 0 and 3\t";
    cin >> row;

    cout << "Choose a column between 0 and 3\t";
    cin >> column;

    if (ships[row][column] == 1)
    {
      ships[row][column] == 0;
      totalships--;
      hits++;
      cout << "Hit !!\t" << (totalships) << "  Ships left" << endl;
    }
    else
    {
      cout << "Miss\n\n";
    }
    numberofturns++;
  }
  cout << "Victory\n\n";
  cout << "You won in : " << numberofturns << "  turns\n";
  for (int i = 0; i < 4; i++)
  {
    for (int j = 0; j < 4; j++)
    {
      cout << ships[i][j] << "\t";
    }
    cout << endl;
  }
  getch();
}
