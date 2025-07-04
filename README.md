<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Student Result (Pass/Fail)</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #111;
      color: #fff;
      text-align: center;
      padding: 2rem;
    }
    input, button {
      padding: 10px;
      font-size: 16px;
      margin: 10px;
    }
    button {
      background: #00ffcc;
      border: none;
      cursor: pointer;
    }
    .result-box {
      margin-top: 20px;
      padding: 20px;
      background: #222;
      display: none;
      border: 1px solid #555;
    }
    .pass { color: #00ff00; }
    .fail { color: #ff4444; }
  </style>
</head>
<body>
  <h1>🎓 Student Result Checker</h1>
  <p>Enter Your Roll Number:</p>
  <input type="text" id="rollInput" placeholder="e.g. 1">
  <button onclick="checkResult()">Check</button>

  <div class="result-box" id="resultBox">
    <h2>Result</h2>
    <p id="statusText"></p>
  </div>

  <script>
    const results = {
      "1": "Pass",
      "2": "Fail",
      "3": "Pass",
      "4": "Pass",
      "5": "Pass",
      "6": "Pass",
      "7": "Pass",
      "8": "Fail",
      "9": "Fail"
    };

    function checkResult() {
      const roll = document.getElementById("rollInput").value;
      const result = results[roll];

      const resultBox = document.getElementById("resultBox");
      const statusText = document.getElementById("statusText");

      if (result) {
        resultBox.style.display = "block";
        if (result === "Pass") {
          statusText.innerHTML = `✅ <strong class="pass">You have Passed!</strong>`;
        } else {
          statusText.innerHTML = `❌ <strong class="fail">You have Failed.</strong>`;
        }
      } else {
        alert("⚠️ No result found for this Roll number.");
        resultBox.style.display = "none";
      }
    }
  </script>
</body>
</html>
