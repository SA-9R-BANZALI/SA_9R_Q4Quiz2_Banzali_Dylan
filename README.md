<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Tuff pink analyzer</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" />
  <style>
    body {
      background-color: #ffe4f2;
      font-family: "Comic Sans MS", cursive, sans-serif;
      color: #d63384;
      text-align: center;
    }

    h1 {
      font-size: 48px;
      margin-top: 40px;
      color: #e91e63;
      font-family: "Cursive";
    }

    #instructions {
      font-size: 20px;
      font-style: italic;
    }

    .subject-btn {
      background-color: #f8bbd0;
      border: none;
      border-radius: 20px;
      padding: 30px;
      margin-bottom: 10px;
      width: 120px;
      height: 120px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 48px;
      font-weight: bold;
      color: #fff;
      box-shadow: 0 5px #d63384;
    }

    .subject-btn:hover {
      background-color: #f48fb1;
    }

    input[type="number"] {
      width: 140px;
      margin-top: 10px;
      border: 2px solid #e91e63;
      border-radius: 10px;
      font-size: 20px;
      text-align: center;
      background-color: #fff0f5;
      color: #c2185b;
    }

    .result-button {
      background-color: #ec407a;
      color: white;
      padding: 15px 40px;
      border: none;
      border-radius: 30px;
      margin-top: 20px;
      font-size: 20px;
      box-shadow: 0 8px #c2185b;
    }

    .result-button:hover {
      background-color: #d81b60;
    }

    #source, footer {
      margin-top: 40px;
      font-size: 16px;
      color: #880e4f;
    }

    .row {
      justify-content: center;
      gap: 20px;
      margin-top: 30px;
    }

    .subject-label {
      margin-top: 10px;
      font-size: 18px;
      font-weight: bold;
      color: #c2185b;
    }
  </style>
</head>
<body>

  <h1>Tuff pink analyzer</h1>

  <details ontoggle="showInstructions()">
    <summary style="font-size: 20px;"> Tap here for a tip!</summary>
    <p id="instructions"></p>
  </details>

  <div class="container mt-4">
    <div class="row">
      <div class="col-md-2">
        <button class="subject-btn" onclick="filipino()">F</button>
        <div id="gr1"></div>
        <div class="subject-label">Filipino</div>
      </div>

      <div class="col-md-2">
        <button class="subject-btn" onclick="english()">E</button>
        <div id="gr2"></div>
        <div class="subject-label">English</div>
      </div>

      <div class="col-md-2">
        <button class="subject-btn" onclick="science()">S</button>
        <div id="gr3"></div>
        <div class="subject-label">Science</div>
      </div>

      <div class="col-md-2">
        <button class="subject-btn" onclick="math()">M</button>
        <div id="gr4"></div>
        <div class="subject-label">Math</div>
      </div>

      <div class="col-md-2">
        <button class="subject-btn" onclick="social()">SS</button>
        <div id="gr5"></div>
        <div class="subject-label">Social Studies</div>
      </div>
    </div>

    <button class="result-button" onclick="AVG()"> Reveal My Rating </button>

    <p id="source">🌸 Note: Grades are for fun and learning! (and your future) Keep growing! 🌸</p>

    <footer>
      <hr />
      <p>💗 Made with love, joy, and hope by <b>Dylan Banzali</b></p>
    </footer>
  </div>

  <script>
    function showInstructions() {
      document.getElementById("instructions").innerText = "Click each subject to input your grade, then tap the pink button to see your score vibe!";
    }

    function filipino() {
      document.getElementById("gr1").innerHTML = "<input type='number' id='Grade1' placeholder='0-100'>";
    }

    function english() {
      document.getElementById("gr2").innerHTML = "<input type='number' id='Grade2' placeholder='0-100'>";
    }

    function science() {
      document.getElementById("gr3").innerHTML = "<input type='number' id='Grade3' placeholder='0-100'>";
    }

    function math() {
      document.getElementById("gr4").innerHTML = "<input type='number' id='Grade4' placeholder='0-100'>";
    }

    function social() {
      document.getElementById("gr5").innerHTML = "<input type='number' id='Grade5' placeholder='0-100'>";
    }

    function AVG() {
      var g1 = Number(document.getElementById("Grade1").value);
      var g2 = Number(document.getElementById("Grade2").value);
      var g3 = Number(document.getElementById("Grade3").value);
      var g4 = Number(document.getElementById("Grade4").value);
      var g5 = Number(document.getElementById("Grade5").value);

      if ([g1, g2, g3, g4, g5].some(isNaN)) {
        alert("Oops! Please enter all 5 grades 💡");
        return;
      }

      var ave = ((g1 + g2 + g3 + g4 + g5) / 5).toFixed(2);

      let vibe = "";

      switch (true) {
        case (ave >= 94 && ave <= 100):
          vibe = "🌟 Outstanding goattt!";
          break;
        case (ave >= 87 && ave <= 93.99):
          vibe = "💖 You’re doing amazing!";
          break;
        case (ave >= 80 && ave <= 86.99):
          vibe = "😊 solid work, keep it up!";
          break;
        case (ave >= 75 && ave <= 79.99):
          vibe = "⚠️ A bit bumpy, but you got this!";
          break;
        case (ave >= 70 && ave <= 74.99):
          vibe = "😓 Needs extra focus!";
          break;
        default:
          vibe = "🚫 Time to hit the books harder!";
      }

      alert("🎯 Your average is " + ave + "\n✨ Rating: " + vibe);
    }
  </script>
</body>
</html>
