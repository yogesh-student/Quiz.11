<!DOCTYPE html>
<html>
<head>
  <title>10 Question Quiz</title>
  <style>
    body { font-family: Arial; padding: 20px; }
    h2 { color: #333; }
    .question { margin-bottom: 20px; }
    .scorecard { margin-top: 30px; border-top: 2px solid #ccc; padding-top: 20px; }
    .correct { color: green; }
    .incorrect { color: red; }
    .skipped { color: orange; }
  </style>
</head>
<body>

  <h2>10 Question Quiz</h2>

  <form id="quizForm">
    <!-- Quiz Questions -->
    <div class="question" id="q1">
      <p>1. Question 1?</p>
      <label><input type="radio" name="q1" value="A"> A</label><br>
      <label><input type="radio" name="q1" value="B"> B</label><br>
      <label><input type="radio" name="q1" value="C"> C</label><br>
      <label><input type="radio" name="q1" value="D"> D</label>
    </div>

    <div class="question" id="q2">
      <p>2. Question 2?</p>
      <label><input type="radio" name="q2" value="A"> A</label><br>
      <label><input type="radio" name="q2" value="B"> B</label><br>
      <label><input type="radio" name="q2" value="C"> C</label><br>
      <label><input type="radio" name="q2" value="D"> D</label>
    </div>

    <div class="question" id="q3">
      <p>3. Question 3?</p>
      <label><input type="radio" name="q3" value="A"> A</label><br>
      <label><input type="radio" name="q3" value="B"> B</label><br>
      <label><input type="radio" name="q3" value="C"> C</label><br>
      <label><input type="radio" name="q3" value="D"> D</label>
    </div>

    <div class="question" id="q4">
      <p>4. Question 4?</p>
      <label><input type="radio" name="q4" value="A"> A</label><br>
      <label><input type="radio" name="q4" value="B"> B</label><br>
      <label><input type="radio" name="q4" value="C"> C</label><br>
      <label><input type="radio" name="q4" value="D"> D</label>
    </div>

    <div class="question" id="q5">
      <p>5. Question 5?</p>
      <label><input type="radio" name="q5" value="A"> A</label><br>
      <label><input type="radio" name="q5" value="B"> B</label><br>
      <label><input type="radio" name="q5" value="C"> C</label><br>
      <label><input type="radio" name="q5" value="D"> D</label>
    </div>

    <div class="question" id="q6">
      <p>6. Question 6?</p>
      <label><input type="radio" name="q6" value="A"> A</label><br>
      <label><input type="radio" name="q6" value="B"> B</label><br>
      <label><input type="radio" name="q6" value="C"> C</label><br>
      <label><input type="radio" name="q6" value="D"> D</label>
    </div>

    <div class="question" id="q7">
      <p>7. Question 7?</p>
      <label><input type="radio" name="q7" value="A"> A</label><br>
      <label><input type="radio" name="q7" value="B"> B</label><br>
      <label><input type="radio" name="q7" value="C"> C</label><br>
      <label><input type="radio" name="q7" value="D"> D</label>
    </div>

    <div class="question" id="q8">
      <p>8. Question 8?</p>
      <label><input type="radio" name="q8" value="A"> A</label><br>
      <label><input type="radio" name="q8" value="B"> B</label><br>
      <label><input type="radio" name="q8" value="C"> C</label><br>
      <label><input type="radio" name="q8" value="D"> D</label>
    </div>

    <div class="question" id="q9">
      <p>9. Question 9?</p>
      <label><input type="radio" name="q9" value="A"> A</label><br>
      <label><input type="radio" name="q9" value="B"> B</label><br>
      <label><input type="radio" name="q9" value="C"> C</label><br>
      <label><input type="radio" name="q9" value="D"> D</label>
    </div>

    <div class="question" id="q10">
      <p>10. Question 10?</p>
      <label><input type="radio" name="q10" value="A"> A</label><br>
      <label><input type="radio" name="q10" value="B"> B</label><br>
      <label><input type="radio" name="q10" value="C"> C</label><br>
      <label><input type="radio" name="q10" value="D"> D</label>
    </div>

    <button type="button" onclick="calculateScore()">Submit</button>
  </form>

  <div class="scorecard" id="result"></div>

  <script>
    const answerKey = {
      q1: "C",
      q2: "C",
      q3: "A",
      q4: "B",
      q5: "B",
      q6: "C",
      q7: "A",
      q8: "D",
      q9: "C",
      q10: "B"
    };

    function calculateScore() {
      let form = document.getElementById("quizForm");
      let resultDiv = document.getElementById("result");
      let totalScore = 0;
      let correct = 0, incorrect = 0, skipped = 0;
      let feedback = "<h3>Scorecard:</h3><ul>";

      for (let i = 1; i <= 10; i++) {
        let qName = "q" + i;
        let selected = form[qName].value;
        if (!selected) {
          totalScore -= 3;
          skipped++;
          feedback += `<li class="skipped">Q${i}: Skipped</li>`;
        } else if (selected === answerKey[qName]) {
          totalScore += 8;
          correct++;
          feedback += `<li class="correct">Q${i}: Correct</li>`;
        } else {
          totalScore -= 21;
          incorrect++;
          feedback += `<li class="incorrect">Q${i}: Incorrect</li>`;
        }
      }

      feedback += "</ul>";
      resultDiv.innerHTML = `
        <p><strong>Total Score:</strong> ${totalScore}</p>
        <p>Correct: ${correct}, Incorrect: ${incorrect}, Skipped: ${skipped}</p>
        ${feedback}
      `;
    }
  </script>

</body>
</html>
