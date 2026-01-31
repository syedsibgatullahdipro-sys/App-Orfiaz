<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Orfiaz•App</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f4f4f4;
    }

    header {
      text-align: center;
      padding: 15px;
      background: #111;
      color: #fff;
    }

    .section {
      background: #fff;
      margin: 15px;
      padding: 15px;
      border-radius: 10px;
    }

    .clock {
      font-size: 28px;
      text-align: center;
      font-weight: bold;
    }

    input, button {
      padding: 10px;
      margin: 5px 0;
      width: 100%;
      font-size: 16px;
    }

    .images img {
      width: 100%;
      margin-top: 10px;
      border-radius: 8px;
    }
  </style>
</head>

<body>

<header>
  <h2>Orfiaz•App</h2>
  <p>Utility Web App</p>
</header>

<div class="section">
  <h3>⏰ Clock</h3>
  <div class="clock" id="clock">00:00:00</div>
</div>

<div class="section">
  <h3>📅 Calendar</h3>
  <input type="date">
</div>

<div class="section">
  <h3>🧮 Calculator</h3>
  <input type="number" id="a" placeholder="First number">
  <input type="number" id="b" placeholder="Second number">
  <button onclick="calc()">Add</button>
  <p id="result"></p>
</div>

<div class="section">
  <h3>🖼️ Image Draft</h3>
  <input type="file" accept="image/*" onchange="preview(this)">
  <div class="images" id="images"></div>
</div>

<script>
  // Clock
  setInterval(() => {
    const now = new Date();
    document.getElementById("clock").innerText =
      now.toLocaleTimeString();
  }, 1000);

  // Calculator
  function calc() {
    const a = Number(document.getElementById("a").value);
    const b = Number(document.getElementById("b").value);
    document.getElementById("result").innerText = "Result: " + (a + b);
  }

  // Image preview
  function preview(input) {
    const img = document.createElement("img");
    img.src = URL.createObjectURL(input.files[0]);
    document.getElementById("images").appendChild(img);
  }
</script>

</body>
</html>
