# googlesheet-grade-calculator
Implement a grade calculator using Google Apps Script that imports grades from Canvas

In many educational settings, Canvas is used to track student progress and assign grades. However, for teachers using a 4-point grading scale, Canvas often doesn't translate grades accurately, causing confusion and inconsistency in final grade calculations. To resolve this, we’ve created a simple Google Sheets grading calculator.

By copying and pasting grades directly from Canvas into this calculator, the Google Apps Script will automatically convert and adjust grades to align with the 4-point scale. This tool ensures accuracy and consistency, giving both teachers and students confidence in their final grades.

Here's a example for 4-points scale:

<img width="698" alt="Screenshot 2024-09-20 at 09 52 02" src="https://github.com/user-attachments/assets/2434ec4a-a658-4a41-8052-8a1642efa037">

If you want to change the grading scale, feel free to change it here((function letter_grade):
'''
function letter_grade(gpa) {
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

'''



