# Grade Book Project

This project will produce a text-based grade book application.

You will need to meet 6 checkpoints for this project before you can develop your final solution. When you complete a checkpoint, make a commit with the comment "Checkpoint #N Complete" where N is the checkpoint number. Checkpoints will be graded on a pass/fail basis (with a late-pass as a possibility) and you must pass a checkpoint in order to receive unit tests and instructions for the next checkpoint. You may not work ahead on checkpoint requirements beyond the checkpoint you are currently working on and doing so will result in not passing your current checkpoint. Grading comments will be left on the most recent commit by the deadline. Not passing a checkpoint means you will need to make another commit correcting your mistakes from the prior grading comments before you can proceed to the next checkpoint. Checkpoints will be graded following Tuesday and Friday commits and a maximum of two checkpoints a week may be passed. When a checkpoint is passed, make sure to perform a pull to receive the newest unit tests and instructions. Checkpoints that are not passed before the final due date will not receive credit (again, you must pass through them sequentially without working ahead of your current checkpoint and you may only pass through a maximum of two a week). Don't alter any file other than Student.java and GradeBook.java. 

Here are the checkpoint due dates for the project and very brief descriptions of the tasks:

1. Exam Average: 10/24
2. Project Scores: 10/31
3. Overall Grades: 11/7
4. Grade Entry: 11/14
5. Import/Export Student Data: 11/21
6. Load/Save Files: 12/5

Checkpoints will not be graded after 12/15 and your last commit on this date will be used for the purposes of determining the final project grade. Additional instructions for your final commit will be posted after you pass checkpoint #6.


## Checkpoint #1 Instructions

Your first task is to complete the implementation of the getExamAverage method in Student.java. A method header has already been included for you. Look at the javadoc comment at the top of the method and implement the method as this comment instructs you to. Check the unit tests for additional guidance. 

**Due: 10/24**


## Checkpoint #2 Instructions

Your second task is to complete the implementation of the getLabScore method in Student.java. A method header has again already been included for you. Look at the javadoc comment at the top of the method but also pay close attention to the new unit tests in StudentTest.java to help you determine how to complete this method. 

**Due: 10/31**

## Checkpoint #3 Instructions

Your third task is to finish up many of the small tasks in the Student class and record all elements of the students' grade. You can see that there are already methods for getting and setting student first and last names. In addition to these, you should add the following methods:

* setParticipationScore - should take a single double value as its only parameter that represents a students' overall participation score for the semester and record it in an instance variable. 
* getParticipationScore - This should be similar to getLabScore.
* setLabScore - should take a single double value as its only parameter that represents a students' overall lab score for the semester and record it in an instance variable. 
* getLabScore - should have no parameters and simply return the recorded lab score for the student. If no score has been recorded, the default should be 0.  *** Important Note: *** In checkpoint 2, you were asked to develop getLabScore as a static method. This was an error and it should have been called getProjectScore (as checkpoints refer to projects). Please rename that method and pay attention to the additional instructions for altering it below. 
* setExam1Score - should take a single double value as its only parameter that represents a students' exam 1 score and record it in an instance variable. 
* getExam1Score - This should be similar to getLabScore.
* setExam2Score - similar to setExam1Score. 
* getExam2Score - This should be similar to getLabScore.
* setExam3Score - similar to setExam1Score. 
* getExam3Score - This should be similar to getLabScore.
* setExam4Score - similar to setExam1Score. 
* getExam4Score - This should be similar to getLabScore.
* setPracticalExamScore - similar to setExam1Score. 
* getPracticalExamScore - This should be similar to getLabScore.
* setProjectScore - The parameters for this method should be, in order: an integer indicating which project's grades are being recorded (1 or 2), and a 6-character-long string holding P, L, or N characters (similar to getLabScore in CP2). This method should simply record the given project score for the student but should retain the detail (the contents of the String).  You will need this information in a later checkpoint. 
* getExamAverage - Alter your existing getExamAverage method to be an instance method with no parameters that computes the exam average based on the instance variables used to store the exam scores for this particular student. 
* getProjectScore - Alter your existing getProjectScore method to be an instance method that has a single parameter (an integer representing the project number -- 1 or 2) and computes and returns the project score based on the stored details of the indicated project. 

As you develop these methods, take a look at the unit tests in StudentTest.java. You'll see that all but two of them are currently commented out. This is so that the tests will compile properly and allow you to test your code as you develop it. Each time you develop a new method, uncomment the unit tests associated with it and test your method out. In a sense, this checkpoint consists of many mini-checkpoints that you'll walk through by hand this way. Once all the tests are uncommented and passing and you believe you have developed your code according to the instructions, make a commit indicating that checkpoint #3 is complete. 

**Due: 11/7**

## Checkpoint #4 Instructions

This checkpoint will involve integrating the work you've performed so far in Student.java with the gradebook application code in GradeBook.java. You've developed a fairly robust datatype for working with a single student record. GradeBook.java holds a number of these student records in a static array (students) and allows a user to perform operations on them. Note that there are two sample students added in to the gradebook. The tests that are run for this checkpoint assume that those two students are present, so don't modify this part of the program (yet -- ultimately you will write code to allow loading this data from a text file). 

Take a look at the switch statement in the heart of the main method. You'll see that a couple of options have been implemented (listing the class roster and closing the program). Your task will be to complete options 3-6 and allow the user to enter new scores for the user. You will use the 'setter' methods you developed in checkpoint #3 to accomplish this. 

Note that each student has a number associated with them (starting at 1) and are stored in an array in which the slot numbers start at 0. Take a look at the implementation of option #2 to see how this discrepancy is dealt with. Understanding this code will help you develop your solutions. Also take a look at the testing code in GradeBookTest.java. This code depends on the 'getter' methods you developed in checkpoint #3 and tests to ensure you're properly updating the data stored in the Student objects. Understanding the code in the test file will also help you understand how both classes (Student and GradeBook) work in tandem.

It is advised that you start with implementing options 5 and 6. These are both fairly simple. First, query the user for the number of the student for whom you will update the score. Read in a single integer on a single line -- this will be the same number that was printed out for the corresponding student in option #2 (implemented for you). Next, query the user for the overall participation / lab grade. Again, read this in as a single double value on a single line. Finally, use the appropriate setter method to update the indicated grade for the indicated student in the array of Student objects.

Once you're passing the tests for options 5 and 5, move on to options 3 and 4. For both of these options, you'll first need to ask the user for the appropriate exam or project to update the grade for. For option 3 (projects), read in an integer from the user indicating the project number. Although the answer will always be 1 or 2, write your code in such a way that additional projects could be added if desired (don't hard-code 1 and 2 -- read an integer in). After that, you will repeat the steps for options 5 and 6 (read in the student number, then the grade). For option 3, do the exact same thing -- read in an integer for the exam. Have "5" represent the practical exam. Then read in the student number and the grade. Note that the "grade" for the project will be the 6-character string you worked with in checkpoint #3.

Below is an example of this interaction for each of the options:

    Welcome to the CM111 Grade Book App!
    
    Please make a selection:
    
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
    
    Please choose an option: 2
    
    1) Turing, Alan
    2) Lovelace, Ada
  
    Please make a selection:
  
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
    
    Please choose an option: 6
  
    Enter the student number: 1
    Enter the participation score: 95
    
    Please make a selection:
  
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
    
    Please choose an option: 5
    
    Enter the student number: 2
    Enter the lab score: 100
    
    Please make a selection:
    
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
    
    Please choose an option: 4
    
    Enter the exam number: 2
    Enter the student number: 1
    Enter the exam score: 80
    
    Please make a selection:
    
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
  
    Please choose an option: 3
  
    Enter the project number: 1
    Enter the student number: 2
    Enter the checkpoint scores as a series of P/L/N characters: PPPPP
    
    Please make a selection:
    
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
    
    Please choose an option: 9
    
    Goodbye!


**Due: 11/14**



## Checkpoint #5 Instructions

To finish off the application, a few more methods are needed in the Student class. We need to be able to create a String that holds all of the data a Student object holds so that we can save that data to a file. This is called serialization. You'll implement a method called serialize in the Student class that create such a String. The String will separate the different values from the Student object using commas. The first value will be the first name, then the last name, then, in order, the lab score, the participation score, the 5 exam scores, and finally the two project scores (1 then 2). Each score will be recorded as a double with the exception of the project scores, which will be saved as the 6-character checkpoint strings. 

It will be important for you to be able to read and interpret the unit tests to help you develop the serialize method. The method is not complex, but there are a lot of opportunities for small errors and mixing up the order of values. Pay close attention to the expected output in the tests and fine-tune your solution until you're passing each of them. You can implement this method by concatenating Strings together and returning the result. Note that printf cannot be used to implement this method (because it cannot build a string you can return -- only print it out). However, the static method format in the String class, which works similarly to printf, can.

Following this, you'll develop a method called deserialize that will take a String as an argument, parse it apart, and import all of the data from this String in to the Student object. The String will be formatted in exactly the same way as the Strings returned by your serialize method. The split method (of the String class) is very helpful for implementing this method.

Finally, you will need to write a method that computes the overall grade for a Student (called getOverallScore). You will use the methods you wrote in checkpoint #3 to accomplish this, and compute a weighted average by multiplying each of these scores by their proportion of the overall course grade (from the syllabus) and sum these values together. The result should be rounded to the nearest point.


**Due: 11/21**


## Checkpoint #6 Instructions

The final checkpoint requires implementation of options #1, #7, and #8 in GradeBook.java. It's recommended that you start by eliminating the "static" block of code at the top of GradeBook.java. Also, remove the comment instructing you to make 'students' private but don't actually make it private -- I've updated the tests to rely on it being public for now. You can make it private on your final submission if you wish.

I've added a new file called samplegrades.txt to your project that will be used instead. Take a look inside the file:

    2
    Alan,Turing,60.0,100.0,100.0,90.0,80.0,70.0,60.0,PLPPPL,PPLLNN
    Ada,Lovelace,80.0,80.0,100.0,90.0,80.0,70.0,60.0,PLPPPL,PPLLNN

Your first task will be to implement option #1. You should ask the user for a filename, create a scanner to read from the file, read the first line and use it to create a new array to store in the variable 'students' (it will indicate the length of this array), and then use a for-loop to populate that array with new student objects, reading a line from the file and using the deserialize method in student to initialize each of the student objects as you go through the loop. 

Once that is complete, implement option #7. You can simply copy and paste option #1 but add in a call to getOverallScore() for each student. 

Finally, implement option #8. This should be option #1 in reverse. Again, ask the user for a filename, but create a PrintWriter object instead that you will use to output all of the data in the GradeBook application. Start by printing a line with the number of students (the length of the students array). Then use a for loop to print out each student's data (print out the value you get back from the serialize() method). Don't forget to close the PrintWriter when you are finished!

Below is a sample of the new interactions you could have with your application:

    Welcome to the CM111 Grade Book App!
    
    Please make a selection:
    
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
    
    Please choose an option: 1
    
    Enter a filename: samplegrades.txt
    
    Please make a selection:
    
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
    
    Please choose an option: 7
    
    1) Turing, Alan: 78 
    2) Lovelace, Ada: 83 
    
    Please make a selection:
    
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
    
    Please choose an option: 6
    
    Enter the student number: 1
    Enter the participation score: 100
    
    Please make a selection:
    
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
    
    Please choose an option: 7
    
    1) Turing, Alan: 82 
    2) Lovelace, Ada: 83 
    
    Please make a selection:
    
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
    
    Please choose an option: 8
    
    Enter a filename: updatedgrades.txt
    
    Please make a selection:
    
    1) Load a gradebook from a file
    2) List Class Roster
    3) Enter Project Grade
    4) Enter Exam Grade
    5) Enter Lab Grade
    6) Enter Participation Score
    7) Print Overall Grades
    8) Save gradebook to a file
    9) Exit
    
    Please choose an option: 9
    
    Goodbye!

Notice that there was an update to Alan Turing's grades, so the new file (updatedgrades.txt) will hold the following:

    2
    Alan,Turing,60.0,60.0,100.0,90.0,80.0,70.0,60.0,PLPPPL,PPLLNN
    Ada,Lovelace,80.0,80.0,100.0,90.0,80.0,70.0,60.0,PLPPPL,PPLLNN

A word of caution: now that your program can overwrite files, be careful what you use for the filename. If you use Student.java, for example, you will overwrite your own code!


**Due: 12/5**
## Final Commit Instructions

Firstly, now that your application is complete and each of the components of your program have been individually tested with unit tests, we can again drop the scaffolding code: make the students array private in GradeBook.java and if you haven't already, remove any code that puts fake student values in the array and rely only on the file-loading functionality.

We will again also drop the assumption that the user never makes a mistake (indeed they do quite often). Your program should not crash or enter an unexpected state when the user makes a mistake, but instead you should display the following message:

    Invalid Response. Try again.
    
Allow the user to correct their error (you may return them to the main menu). You may need to use additional while loops and a little creativity to get this to work in every case.

Although it is reasonable to also validate the contents of the grades file when loading one with option #1, validating this data will be optional. That is, if there are errors in the format of the file, you won't be held responsible for detecting them, but if you have extra time and want a challenge, you are encouraged to try!

Unlike the other checkpoints, there is no requirement that you pass some number of tests in order to proceed. I have reserved some hidden tests for this task that I will manually test your code with after the due date. 

It does help to leave a message with your final commit stating "final commit" so that I know you didn't accidentally miss the deadline, but your latest commit (whatever it is) will be graded immediately after the due date and no late commits will be accepted. Your "hidden testing" score will be proportional to the number of hidden tests your code passes, so if you seek a high score for the project, be sure to test your code thoroughly.

Part of your score will also be determined by how you've personally tested your code before your final commit. Don't forget to submit a log of your personal tests (copy and paste testing transcripts from the terminal in to the assignment on D2L so I can look over how you tested your code). 

Lastly, style will be considered as part of your project score in your final commit. Make sure to follow all listed style guidelines in the online text. You should also receive some feedback on style in comments on your prior checkpoint commits. 

**Due: 12/15**
