
const sheets = SpreadsheetApp.getActiveSpreadsheet().getSheets()[0];

var semesterGrade = 0;
var semesterGradeRounded = 0;
var semesterGradeSheet = SpreadsheetApp.getActiveSpreadsheet();

if (SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Grades")== null){
  semesterGradeSheet.insertSheet("Grades")
}

const gradesheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Grades");
gradesheet.clearContents();
gradesheet.getRange(1,1).setValue("Student Name")
gradesheet.getRange(1,2).setValue("Homework Grade")
gradesheet.getRange(1,3).setValue("Quizzes Grade")
gradesheet.getRange(1,4).setValue("Test Grade")
gradesheet.getRange(1,5).setValue("Overall Grade")
gradesheet.getRange(1,7).setValue("Overall Grade(Not rounded)")
gradesheet.getRange(1,6).setValue("Overall letter Grade")


function onOpen() {
  SpreadsheetApp.getUi()
    .createMenu('Calculate Grade')
    .addItem('Calculate', 'myFunction')
    .addToUi();
}

function myFunction() {
  var homework = [];
  var quizzes = [];
  var tests = [];

  function listtoarray(student_num){
    for(var i = 6;i<=sheets.getLastColumn();i++){
      assignmentname = sheets.getRange(1,i).getValue();
      if (assignmentname.indexOf("HW") ==0 && sheets.getRange(student_num,i).getValue() != "N/A"&&sheets.getRange(student_num, i).getValue() !== ""){
        homework.push(sheets.getRange(student_num,i).getValue())
      }
      if(assignmentname.indexOf("Quiz")>=0 && assignmentname.indexOf("Official")>=0 && sheets.getRange(student_num,i).getValue() != "N/A" && sheets.getRange(student_num, i).getValue() !== ""){
        quizzes.push(sheets.getRange(student_num,i).getValue())
      }
      if(assignmentname.indexOf("Test") >=0 && assignmentname.indexOf("Unit") >=0 && assignmentname.indexOf('Official') >= 0 && sheets.getRange(student_num,i).getValue() !== "N/A"){
        tests.push(sheets.getRange(student_num,i).getValue())
      }
    }
  }

  function return_grade(p_array){
    var total_point = 0;
    for(var i = 0;i<p_array.length; i++) {
      total_point+= p_array[i]
    }
    return total_point/p_array.length
  }

  for(var i = 4;i<=sheets.getLastRow();i++){
    var homework = [];
    var quizzes = [];
    var tests = [];
    listtoarray(i);
    var quizGrade = (return_grade(quizzes))
    var homeworkGrade = (return_grade(homework))
    var testGrade = (return_grade(tests))
    semesterGrade = .15 * homeworkGrade + .25 * quizGrade + .60 * testGrade
    semesterGradeRounded = semesterGrade.toFixed(1);


    gradesheet.getRange(i-2,1).setValue(sheets.getRange(i,1).getValue());
    gradesheet.getRange(i-2,2).setValue(homeworkGrade.toFixed(3));
    gradesheet.getRange(i-2,3).setValue(quizGrade.toFixed(3));
    gradesheet.getRange(i-2,4).setValue(testGrade.toFixed(3));

    gradesheet.getRange(i-2,5).setValue(semesterGradeRounded);
    gradesheet.getRange(i-2,6).setValue(letter_grade(semesterGradeRounded));
    gradesheet.getRange(i-2,7).setValue(semesterGrade)

  
  }


}

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


