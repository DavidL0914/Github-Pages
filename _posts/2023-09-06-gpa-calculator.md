---
toc: false
comments: true
layout: post
title: GPA Calculator
description: A GPA Calculator built with js!
courses: { csp: {week: 3} }
type: hacks
---

<html>
<head>
  <title>GPA Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
    }

    h1 {
      text-align: center;
      color: #333;
    }

    form {
      background-color: #fff;
      padding: 20px;
      border-radius: 5px;
      box-shadow: 0px 0px 10px #aaa;
      max-width: 400px;
      margin: 0 auto;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 10px;
    }

    th, td {
      padding: 10px;
      text-align: left;
      border-bottom: 1px solid #ddd;
    }

    select, input[type="text"] {
      width: 100%;
      padding: 8px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }

    input[type="button"] {
      background-color: #333;
      color: #fff;
      border: none;
      padding: 10px 20px;
      cursor: pointer;
    }

    #gpa {
      margin-top: 20px;
      text-align: center;
      font-size: 24px;
      color: #333;
    }
  </style>
</head>
<body>
    <br>
  <h1>GPA Calculator</h1>

  <form name="grades">
    <table id="gradeTable">
      <thead>
        <tr>
          <th>Class</th>
          <th>Weight</th>
          <th>Grade</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><input type="text"></td>
          <td>
            <select name="weight1">
              <option value="regular">Regular</option>
              <option value="ap">AP</option>
            </select>
          </td>
          <td>
            <select name="grade1">
              <option value="none" selected>Grade</option>
              <option value="a">A</option>
              <option value="b">B</option>
              <option value="c">C</option>
              <option value="d">D</option>
              <option value="f">F</option>
            </select>
          </td>
        </tr>
      </tbody>
    </table>
    <input type="button" value="Add Row" onClick="addRow()">
    <br><br>
    <input type="button" value="Calculate GPA" onClick="calculate()">
    <input type="button" value="Reset" onClick="reset()">
  </form>

  <div id="gpa"></div>
</body>
</html>

  <script>
    var rowCount = 1;

    var addRow = function() {
      rowCount++;
      var table = document.getElementById("gradeTable");
      var row = table.insertRow(rowCount);
      var cell1 = row.insertCell(0);
      var cell2 = row.insertCell(1);
      var cell3 = row.insertCell(2);
      cell1.innerHTML = '<input type="text">';
      cell2.innerHTML = `
        <select name="weight${rowCount}">
          <option value="regular">Regular</option>
          <option value="ap">AP</option>
        </select>`;
      cell3.innerHTML = `
        <select name="grade${rowCount}">
          <option value="none" selected>Grade</option>
          <option value="a">A</option>
          <option value="b">B</option>
          <option value="c">C</option>
          <option value="d">D</option>
          <option value="f">F</option>
        </select>`;
    };
var createWeightsArray = function(weight1, weight2, weight3, weight4, weight5, weight6, grade1, grade2, grade3, grade4, grade5, grade6) {
  var weights = [];
  
  if(grade1 !== "none") {
    weights.push(weight1)
  } if(grade2 !== "none") {
    weights.push(weight2)
  } if(grade3 !== "none") {
    weights.push(weight3)
  } if(grade4 !== "none") {
    weights.push(weight4)
  } if(grade5 !== "none") {
    weights.push(weight5)
  } if(grade6 !== "none") {
    weights.push(weight6)
  } 
  
  return weights;
};

var createGradesArray = function(grade1, grade2, grade3, grade4, grade5, grade6) {
  var grades = [];
  
  if(grade1 !== "none") {
    grades.push(grade1)
  } if(grade2 !== "none") {
    grades.push(grade2)
  } if(grade3 !== "none") {
    grades.push(grade3)
  } if(grade4 !== "none") {
    grades.push(grade4)
  } if(grade5 !== "none") {
    grades.push(grade5)
  } if(grade6 !== "none") {
    grades.push(grade6)
  } 
  
  if(grades.length > 0) {
    return grades;
  } else {
    alert("Please enter at least one grade.")
  }
};

var convert = function(grades) {
  var convertedGrades = [];

  for (var i = 0; i < grades.length; i++) {
    switch (grades[i]) {
      case 'a':
        convertedGrades.push(4.0);
        break;
      case 'b':
        convertedGrades.push(3.0);
        break;
      case 'c':
        convertedGrades.push(2.0);
        break;
      case 'd':
        convertedGrades.push(1.0);
        break;
      case 'f':
        convertedGrades.push(0.0);
        break;
      default:
        convertedGrades.push(0.0); // Handle 'none' or unknown grades as 0.0
        break;
    }
  }

  return convertedGrades;
};


var weight = function(weights, grades) {
  for(var i = 0; i < grades.length; i++) {
    var num = grades[i].toString();
    if(weights[i] === "ap") {
      if(grades[i] === "0") {
        grades[i] = grades[i] + 0;
      } else {
        grades[i] = grades[i] + 1;
      }
    }
  }
  
  return grades;
};

var averageGrades = function(grades) {
  var x = 0;
  
  for(var i = 0; i < grades.length; i++) {
    x = x + grades[i]
  }
  
  return x / grades.length;
};

var printToDiv = function(gpa) {
  document.getElementById("gpa").innerHTML = gpa
};

var calculate = function() {
  var totalPoints = 0;
  var totalWeight = 0;
  var validRowCount = 0;

  for (var i = 1; i <= rowCount; i++) {
    var weight = document.grades[`weight${i}`].value;
    var grade = document.grades[`grade${i}`].value;

    if (grade !== "none" && grade !== "") {
      var numericGrade = convert([grade])[0]; // Convert grade to numeric value

      if (weight === "ap") {
        numericGrade += 1; // Add 1 point for AP courses
      }

      totalPoints += numericGrade; // Add the grade points to totalPoints
      totalWeight += (weight === "ap") ? 5 : 4; // Update the totalWeight based on the weight type
      validRowCount++;
    }
  }

  if (validRowCount > 0) {
    var gpa = totalPoints / validRowCount; // Divide by validRowCount to get the average GPA
    printToDiv(gpa.toFixed(2)); // Display GPA with 2 decimal places
  } else {
    alert("Please enter at least one grade.");
  }
};