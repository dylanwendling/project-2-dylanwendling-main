# TicTacToe Project

This project will produce a text-based, multi-player tic-tac-toe game.

You will need to meet 6 checkpoints for this project before you can develop your final solution. When you complete a checkpoint, make a commit with the comment "Checkpoint #N Complete" where N is the checkpoint number. Checkpoints will be graded on a pass/fail basis (with a late-pass as a possibility) and you must pass a checkpoint in order to receive unit tests and instructions for the next checkpoint. You may not work ahead on checkpoint requirements beyond the checkpoint you are currently working on and doing so will result in not passing your current checkpoint. Grading comments will be left on the most recent commit by the deadline. Not passing a checkpoint means you will need to make another commit correcting your mistakes from the prior grading comments before you can proceed to the next checkpoint. Checkpoints will be graded following Tuesday and Thursday commits and a maximum of two checkpoints a week may be passed. When a checkpoint is passed, make sure to perform a pull to receive the newest unit tests and instructions. Checkpoints that are not passed before the final due date will not receive credit (again, you must pass through them sequentially without working ahead of your current checkpoint and you may only pass through a maximum of two a week). Don't alter any file other than TicTacToe.java. 

Here are the checkpoint due dates for the project and very brief descriptions of the tasks:

1. Drawing the board: 8/29
2. Tracking moves with variables: 9/5
3. User initialization of board state: 9/12
4. Allow users to make a move: 9/26
5. Determine a winner: 10/3
6. Take turns making moves: 10/10

Checkpoints will not be graded after 11/22 and your last commit on this date will be used for the purposes of determining the final project grade. Additional instructions for your final commit will be posted after you pass checkpoint #6.


## Checkpoint #1 Instructions

Write some print statements in your main method that use spaces, |, and - symbols to print an empty tic-tac-toe board. Include dots for each empty spot on the board (including the empty spots in the third column). When you're finished, your program should print exactly what is below. 

	.|.|.
	-----
	.|.|.
	-----
	.|.|.

When your code is passing the unit tests, make a commit with the comment "Checkpoint #1 Complete". 

**Due: 9/04**

## Checkpoint #2 Instructions

You will now keep track of what marks have been made on the tic-tac-toe board using characters. A dot character `'.'` will indicate no move has been made while an `'X'` or `'O'` character will determine that corresponding player has left a mark. Define 9 different variables of type `char` and name them `b11`, `b12`, `b13` for the slots in the first row; `b21`, `b22`, `b23`, for the slots in the second row; and `b31`, `b32`, `b33` for the last row. Initialize all of these variables to `' '` except for `b11` and `b12` which should be `'X'` and `'O'`, respectively. Use printf and the `%c` escape to print the contents of your 9 variables on the board. Your unit test has been updated to expect the X and O to be printed appropriately, and your final commit should have just `b11` and `b12` set to values other than dot, but try some other values out to see that your print statements are working properly with the variables before you commit. When you're ready to commit, your code should print the following exactly:


	X|O|.
	-----
	.|.|.
	-----
	.|.|.

Note that you can pass the unit test here without following the instructions properly. If you don't follow the instructions (you don't use variables and printf), the instructor will not pass you on to the next checkpoint when grading your work. When your code is ready, make a commit with the comment "Checkpoint #2 Complete".

**Due: 9/11**

## Checkpoint #3 Instructions

Now develop some code that will read initial values in from the user and assign them to the 9 board variables. You should use a prompt exactly like the line below:

    Enter value for row 1 column 1: 

Note that there should be a single space following the colon (:) and no new line. The user should be able to respond with either an X, a O, or a dot. Record their response in the appropriate variable. Note that the `Scanner`'s `nextLine()` method will return a `String`, but you will need a character. You can convert the response to a character by calling the charAt(0) method (you'll learn more ways to use this method in the next unit). All together, you can call `nextLine().charAt(0)` to read a single character in from the user. 

Now repeat this 9 times, changing only the row number and column number in the prompt. This will involve a lot of tedious copying and pasting, but bear in mind that you will learn a tidier and faster way to write this kind of code in the future! 

First read in each value for the first row, in order from left to right. Then the second row, and finally the third, in the same internal order. If your checkpoint #2 code is correct, after reading the values from the user, your code should properly display each value on the board. 

For now you can assume that the user will correctly either enter an X, O, or a dot. Don't worry about the user of the program making a mistake for this checkpoint. 

For this checkpoint there are several unit tests with varied input for which your program must produce a correlating output. When your code is passing each of these tests, make a commit with the comment "Checkpoint #3 Complete". 

**Due: 9/18**

## Checkpoint #4 Instructions

Now develop some code that will assume it is X's turn to make a move and allow them to update the board with their move. Add this code to the end of your main method. Do not remove the code you developed for CP3 that initializes each of the 9 board variables to a value provided by the user. All of your new code should be added *following* this code in your main method.

Your new code should start by identifying whose turn it is (for now it will always be X's turn) and then ask for the coordinates they would like to use for their move:

    It is Y's turn
    Enter row for move (1-3): 
    Enter column for move (1-3): 

The user should be able to enter an integer value at the end of the second line and at the end of the third line. Again, note that there should be a single space after the colon and no new line. 

You will now need to use if statements to determine which variable to update. Again, there will be some copying and pasting involved and your code will look longer than it should be, but you will learn ways to shorten it later. Also, again, don't worry about the user entering an invalid response. Use an if/else chain to update the correct variable (9 possibilities) to hold the value X. 

Lastly, copy and paste your code to print the board so that your program prints the board for a second time. This way you can test to see that it is working as expected. For example, if the user initializes the board as they did in the example for the last checkpoint, then moves to row 2 and column 2, your program should print out the following:

	X|O|.
	-----
	.|X|.
	-----
	.|.|.

When your code is passing each of the new unit tests (and each of the old ones), make a commit with the comment "Checkpoint #4 Complete". 

Due: 9/25

## Checkpoint #5 Instructions

Now you'll add some code that will determine if there is a winner. This will need to be added before the code you added in the last checkpoint to make a move for player X and, for now, will depend solely on the initialization of the board (it should be added after that code). There are 8 ways to get three in a row and win tic-tac-toe so you should create 8 if statements, one for each winning scenario. If a player wins (they have three in a row on the board), print out the result with the following message: 

    Game Over: X wins 

Your message should be exactly the same as the one above where only the X may differ in the case that O wins. If neither player wins and there is not an open space on the board for a move, your program should print the following message:

    Game Over: no winner

When your code is passing each of the new unit tests (and each of the old ones), make a commit with the comment "Checkpoint #5 Complete". 

Due: 10/2

## Checkpoint #6 Instructions

Your last checkpoint will involve making the game fully playable by two players sharing a keyboard. Use a while loop to repeatedly ask each player (both X and O) for their move and update the board, halting the program with the message from checkpoint #5 when there is a winner or no remaining moves. For now, you can still assume that the user will not make mistakes when entering data.  

With a little cleverness and an extra variable determining whose turn it is, you can avoid having to copy and paste any more code. You should strive to do so for this checkpoint but it won't be required to pass the checkpoint. However, unnecessary copying and pasting will be considered "bad style" on the grading rubric. 

When your code is passing each of the new unit tests (and each of the old ones), make a commit with the comment "Checkpoint #6 Complete". 

**Due: 10/9**

## Final Commit Instructions

Firstly, now that your game is playable and each of the components of your program have been individually tested with unit tests, we can drop the "scaffolding" code we've been using to manually initialize all 9 board variables (the code you developed for CP3). Remove this code from your program and simply initialize each variable to '.'. 

We will also drop the assumption that the user never makes a mistake (indeed they do quite often). Your program should not crash or continue when the user makes a mistake, but instead you should display exactly the following message:

    Invalid Response. Try again.
    
Then, on the next line, repeat the prompt and allow the user to try again until they get it right. You may need to use additional while loops and a little creativity to get this to work in every case.

Unlike the other checkpoints, there is no requirement that you pass some number of tests in order to proceed. I have reserved some hidden tests for this task that I will manually test your code with after the due date. 

It does help to leave a message with your final commit stating "final commit" so that I know you didn't accidentally miss the deadline, but your latest commit (whatever it is) will be graded immediately after the due date and no late commits will be accepted. Your "hidden testing" score will be proportional to the number of hidden tests your code passes, so if you seek a high score for the project, be sure to test your code thoroughly.

Part of your score will also be determined by how you've personally tested your code before your final commit. Don't forget to submit a log of your personal tests (copy and paste testing transcripts from the terminal in to the assignment on D2L so I can look over how you tested your code). 

Lastly, style will be considered as part of your project score in your final commit. Make sure to follow all listed style guidelines in the online text. You should also receive some feedback on style in comments on your prior checkpoint commits. 

Note that you've learned more by now about how to write shorter, more efficient code by using data structures such as arrays, you could refactor your prior code from your older commits and make your code more elegant with less repetition. More compact code is usually easier to maintain in large projects with lots of changes over time. This is not required for credit but may improve your style score if you lose points for other reasons. 

**Due: 11/22**
