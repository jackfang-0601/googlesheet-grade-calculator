# googlesheet-grade-calculator
Implement a grade calculator using Google Apps Script that imports grades from Canvas

# The google app script code is on [this file](https://github.com/jackfang-0601/googlesheet-grade-calculator/blob/main/code.gs)

In many educational settings, Canvas is used to track student progress and assign grades. However, for teachers using a 4-point grading scale, Canvas often doesn't translate grades accurately, causing confusion and inconsistency in final grade calculations. To resolve this, we’ve created a simple Google Sheets grading calculator.

By copying and pasting grades directly from Canvas into this calculator, the Google Apps Script will automatically convert and adjust grades to align with the 4-point scale. This tool ensures accuracy and consistency, giving both teachers and students confidence in their final grades.

Here's a example for 4-points scale:

<img width="698" alt="Screenshot 2024-09-20 at 09 52 02" src="https://github.com/user-attachments/assets/2434ec4a-a658-4a41-8052-8a1642efa037">

If you want to change the grading scale, feel free to change it on the code((function letter_grade):

```function letter_grade(gpa) {
  if (gpa >= 3.7) {
    return "A";
  } else if (gpa >= 3.5) {
    return "A-";
  } else if (gpa >= 3.1) {
    return "B+";
  } else if (gpa >= 2.8) {
    return "B";
  } else if (gpa >= 2.5) {
    return "B-";
  } else if (gpa >= 2.1) {
    return "C+";
  } else if (gpa >= 1.8) {
    return "C";
  } else if (gpa >= 1.5) {
    return "C-";
  } else if (gpa >= 1.1) {
    return "D+";
  } else if (gpa >= 0.8) {
    return "D";
  } else if (gpa >= 0.5) {
    return "D-";
  } else {
    return "F";
  }
}
```

# Sets up the code and sheet

1. Create a New Google Sheet:
   Go to https://docs.google.com/spreadsheets/create
   or click the "New" button in your Google Drive and select "Google Sheets."

 
2. Write or Paste Your Code:
   Go the the sheet you just created and right-click extention and select Google App script
<img width="770" alt="Screenshot 2024-09-20 at 10 09 46" src="https://github.com/user-attachments/assets/59a448e7-1c4d-4b7c-9099-7751f496161f">

 After opening up the google app scirpt page, copy paste the code([this file](https://github.com/jackfang-0601/googlesheet-grade-calculator/blob/main/code.gs))


# Runing the code
Select run on your google app script page 

After you run it, go back to the google sheet you just created. 

You can see a buttom called Calculate grade and click the buttom 
<img width="843" alt="Screenshot 2024-09-20 at 10 14 05" src="https://github.com/user-attachments/assets/b177312e-a792-4242-89d7-d108f9227412">

Here's a example:
<img width="1448" alt="Screenshot 2024-09-20 at 10 19 24" src="https://github.com/user-attachments/assets/b15fd6aa-5ec0-429a-b6e7-697db16ea53c">

On your bottom left corner, you see a new sub-sheet just got created. That's the grade after calculation. 
<img width="859" alt="Screenshot 2024-09-20 at 10 22 20" src="https://github.com/user-attachments/assets/fbee3933-63d7-4f09-981e-d5d3bee5debd">


# Naming rule for assigments 

Homework: HW + numbers   HW[1] or HW 1 both works 

Quiz: Quiz + numbers For example: Quiz 1 Unit 1 Quiz

Test: Test+ numbers For example: Test 1, Unit 1 Test

In this version of the grading calculator, there isn't a specific category for projects, so they are grouped together with quizzes under the same category. To ensure the code correctly processes the grades for each assignment, you will need to specify “quiz”. This will allow the script to appropriately identify and calculate scores based on the quiz grading criteria.
Feel free to put "homework" or "test" , it also works. It will just calcucalte the category you wanted to be. 

Here are some example:

  Project 1(Quiz)

  Final Project(Test)


# Contact info

If you have any question. Feel free to email me or ask a question on this page.

My email is jackfang0601@gmail.com


Thank you for 





   
   







