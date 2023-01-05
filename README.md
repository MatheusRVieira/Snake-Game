# CPPND: Capstone Snake Game

* This project is an extension of the Snake game in C++. The code for this repo was inspired by [this](https://codereview.stackexchange.com/questions/212296/snake-game-in-c-with-sdl) excellent StackOverflow post and set of responses.

<img src="snake_game.gif"/>

* The following additional features were added:
  * Player's score is saved as a .txt file in /build. The game prints that score (if greater than zero) was saved whenever game is finished. The game prints when the record is beaten (if exists), as well. The logic was implemented in *SaveScore()* and *GetPreviousScores()*, in the *game* class.
  * Pause and unpause the game when pressing ESC and prints it. The logic was implemented in *CheckGameIsPaused(Controller const&, bool&)*, as its overloads functions, *CheckGameIsPaused(int &)* and *CheckGameIsPaused(int &, bool &)*, in the *game* class.
  * Increase the snake speed by 0.01 when pressing SCAPE and prints it. The logic was implemented in *IncreaseSpeed(Snake &) const*, in *controller* class.

## Rubric points adressed
1. The project makes use of references in function declarations:
  * Please, refer to *CheckGameIsPaused(int &)* and its overloaded functions, in *game* class, where *tempPause* reference is modified. Also, in *IncreaseSpeed(Snake &) const*, in *controller* class, where *snake* is passed as reference, in order to modify *snake.speed*.
2. The project reads data from a file and process the data, or the program writes data to a file: 
  * *GetPreviousScores()*, in the *game* class, reads data from a file, if exists, to retrieve the previous record. *SaveScore()*, in the *game* class, writes data to the same file, in order to save the player's score.
3. The project demonstrates an understanding of C++ functions and control structures:
  * Please, notice that each feature added was implemented in its own function, using control structures, as if, else, while, and ternary operator. A namespace *Path* was added, too.
4. Templates generalize functions in the project:
  *  *GetPreviousScores()*, in the *game* class, is a template.
5. The project uses Object Oriented Programming techniques:
  * Please, notice that the features were added using class methods in *game* class and *Controller* class, each one perfoming its task. Also, *snake* class holds the data, *pause*, used by *CheckGameIsPaused(Controller const&, bool&)*, and its overloads functions.
6. Classes use appropriate access specifiers for class members:
  * In fact, all class data members are explicitly specified as public, protected, or private in *game*, *controller* and *snake* classes.
7. Overloaded functions allow the same function to operate on different parameters:
  * *CheckGameIsPaused(Controller const&, bool&)*, in the *game* class, is overloaded twice, namely, *CheckGameIsPaused(int &)* and *CheckGameIsPaused(int &, bool &)*.
8. The project accepts user input and processes the input:
  * The user can pause and unpause the game pressing *ESCAPE*, and increase the speed of the snake pressing *SPACE*. Both user's inputs are catched and processed while the game is running.  

## Dependencies for Running Locally
* cmake >= 3.7
  * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* SDL2 >= 2.0
  * All installation instructions can be found [here](https://wiki.libsdl.org/Installation)
  >Note that for Linux, an `apt` or `apt-get` installation is preferred to building from source. 
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools](https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)

## Basic Build/Run Instructions

1. Clone this repo.
2. Make a build directory in the top level directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./SnakeGame`.

* If you're using WSL 2 on Windows 10, before running `./SnakeGame`:
  * Install and run XLaunch. 
  * Check the box "No access control"
  * Run: `export DISPLAY=192.168.112.1:0.0` where 192.168.112.1 is the WSL ipv4 address 

## CC Attribution-ShareAlike 4.0 International


Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg