---
description: Here are the some amazing Programming codes which I created when I was bored
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 👩‍💻 Fun Programming Codes

## 1. CPP Codes

```cpp
#include <iostream>
#include <vector>
#include <windows.h>
using namespace std;

// Print Disco Colors in terminal
int main() {
    vector<string> combinations = {"00","10","20","30","40","50","60","70","80",
    "90","a0","b0","c0","d0","e0","f0"};
    
    cout << "\n\n\t\tThis is Disco\n\n\t\t";

    while (true) {
        for (const string& combination : combinations) {
            string command = "color " + combination;
            system(command.c_str());
            Sleep(100);
        }
    }
}

```

```cpp
#include <iostream>
#include <windows.h>

using namespace std;

// Loading Screen in C++
void loadingBar()
{
	system("cls");
	system("color 9F");

	char a = 177, b = 219;
	// cout<<"\n\n\n\n\n\t\t\t\t\tStudent's Data Management System";
	cout << "\n\t\t\t\t\tLoading Screen By Raunak Gupta";
	cout << "\n\n\n\t\t\t\t\tLoading...\n";
	cout << endl;
	cout << "\t\t\t\t\t";

	for (int i = 0; i < 26; i++)
	{	
		cout << a;
	}
	cout << "\r";
	cout << "\t\t\t\t\t";
	for (int i = 0; i < 26; i++)
	{
		cout << b;
		Sleep(200);
	}
}

int main()
{
	loadingBar();
}

```

```cpp
#include <bits/stdc++.h>
#include <chrono> // Include for chrono
#include <thread> // Include for this_thread
using namespace std;

// Hacker Like Output in terminal
int main()
{
    string Word;
    cout << "Enter a string: ";
    getline(cin, Word);

    string Letters = "abcdefghijklmnopqrstuvwxyz ";
    string target_word = "";
    int Counter = 0, random_number;

    srand(time(0)); // Seed the random number generator with current time

    while (target_word != Word)
    {
        random_number = rand() % Letters.length();

        if (Letters[random_number] == Word[Counter])
        {
            target_word += Word[Counter];
            Counter++;
            this_thread::sleep_for(chrono::duration<double, std::ratio<1, 2>>(0.1));
            cout << target_word << endl;
        }
        else
        {
            this_thread::sleep_for(chrono::duration<double, std::ratio<1, 2>>(0.1));
            cout << target_word + Letters[random_number] << endl;
        }
    }

    return 0;
}

```

```cpp
#include <iostream>
using namespace std;

// Performing Loop without using loop in c++
int main()
{
    int x=0;
    
s:
    cout << ++x << "  ";
    if (x >= 10)
    exit;
    else
    goto s;
}

```

## 2. C Programming

```c
#include <stdio.h>

// Color Palet Code
int main()
{
    int i, j;
    for (i = 0; i < 8; i++)
    {
        for (j = 0; j < 8; j++)
        {
            printf("\033[1;%d;%dm", 30 + i, 40 + j);
            printf("Color %d-%d", i, j);
            printf("\033[0m\t");
        }
        printf("\n");
    }
}
//    printf("\033[31m"); // set text color to red
//    printf("This text is red!\n");
//    printf("\033[43m"); // set background color to yellow
//    printf("This text has a yellow background!\n");
//    printf("\033[1m"); // set text to bold
//    printf("This text is bold!\n");
//    printf("\033[0m"); // reset text color and style

```

```c
#include <stdio.h>

// ForeGround Color
int main()
{
    int i;
    printf("\t------------------------------------------------\n");
    printf("\t\tColors in c Programming\n\n");
    for (i = 0; i < 8; i++)
    {
        printf("\033[1;%dm", 30 + i);
        printf("\t\tYou what's uppppp!!!!!\n");
    }
    printf("\t------------------------------------------------\n");
}
```

## 3. Python Codes

```python
# Making Taskmanager unresponsive
import time
big_list = []
while True:
    big_list.append('A' * 10965757868)
    time.sleep(0.1)

```

```python
# Downloading YT playlist

import yt_dlp

playlist_url = 'https://www.youtube.com/playlist?list=PL6gx4Cwl9DGCkg2uj3PxUWhMDuTw3VKjM'

ydl_opts = {
    'outtmpl': '%(title)s.%(ext)s',
}

with yt_dlp.YoutubeDL(ydl_opts) as ydl:
    ydl.download([playlist_url])
```

## 4. VBS Codes

### Some cool Bombing script

```vb
do
msgbox "Potential Virus Found"
loop
```

```vb
name=inputbox("Whats your name?                                                                                                                         Please write your name in the box below :                                                                                            Created by Raunak", "Your Name")

msgbox("Have a good day ") + name
msgbox("Don't forget to change your nappy ") + name
msgbox("Hahahahahaha ")
```

```vb
Set wshShell = wscript.CreateObject("WScript.Shell")
do
wscript.sleep 100
wshshell.sendkeys "~(enter)"
loop
```

```vb
Set wshShell = wscript.CreateObject("WScript.Shell")
do
wscript.sleep 100
wshshell.sendkeys "~(enter)"
loop
```

```vb
Set raunak = CreateObject("WScript.Shell") 
raunak.run "Notepad" 
WScript.Sleep 100
raunak.sendkeys "H"
WScript.Sleep 100
raunak.sendkeys "I"
WScript.Sleep 100
raunak.sendkeys " "
WScript.Sleep 100
raunak.sendkeys "T"
WScript.Sleep 100
raunak.sendkeys "H"
WScript.Sleep 100
raunak.sendkeys "I"
WScript.Sleep 100
raunak.sendkeys "S"
WScript.Sleep 100
raunak.sendkeys " "
WScript.Sleep 100
raunak.sendkeys "I"
WScript.Sleep 100
raunak.sendkeys "S"
WScript.Sleep 100
raunak.sendkeys " "
WScript.Sleep 100
raunak.sendkeys "A"
WScript.Sleep 100
raunak.sendkeys "U"
WScript.Sleep 100
raunak.sendkeys "T"
WScript.Sleep 100
raunak.sendkeys "O"
WScript.Sleep 100
raunak.sendkeys "T"
WScript.Sleep 100
raunak.sendkeys "Y"
WScript.Sleep 100
raunak.sendkeys "P"
WScript.Sleep 100
raunak.sendkeys "I"
WScript.Sleep 100
raunak.sendkeys "N"
WScript.Sleep 100
raunak.sendkeys "G"
WScript.Sleep 100
raunak.sendkeys "!"
WScript.Sleep 100
raunak.sendkeys "!"
```

## Batch Code

```bat
:start
   start
   goto start
```

```bat
@echo off
setlocal enabledelayedexpansion

REM Define an array of combinations
set "combinations=ff fe fd fc fb fa f9 f8 f7 f6 f5 f4 f3 f2 f1 ef ee ed ec eb ea e9 e8 e7 e6 e5 e4 e3 e2 e1 df de dd dc db da d9 d8 d7 d6 d5 d4 d3 d2 d1 cf ce cd cc cb ca c9 c8 c7 c6 c5 c4 c3 c2 c1 bf be bd bc bb ba b9 b8 b7 b6 b5 b4 b3 b2 b1 af ae ad ac ab aa a9 a8 a7 a6 a5 a4 a3 a2 a1 9f 9e 9d 9c 9b 9a 99 98 97 96 95 94 93 92 91 8f 8e 8d 8c 8b 8a 89 88 87 86 85 84 83 82 81"

REM Split the combinations into an array
for %%c in (%combinations%) do (
    color %%c
    echo Color Bombo %%c
    REM Add your command here to run the combination, for example:
    REM echo %%c >> output.txt
    REM Replace the above line with your actual command
)
color 07

```

```bat
:1
start cmd.exe
goto 1
```

```bat
@echo off
for /L %%i in (1,1,5) do (
    echo %%i
)
::@echo off: This line turns off command echoing, so you don't see 
::each command as it is executed in the console.

::for /L %%i in (1,1,5) do This is the for loop structure. 
::It uses the /L option to indicate that it's a numeric loop. %%i is the loop 
::variable that will hold the current value. (1,1,5) specifies the range: start from 1, increment by 1, and end at 5.

::echo %%i: This line inside the loop echoes the current value of %%i to 
::the console.

```
