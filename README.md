<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>塩分濃度計算</title>
  <style>
    body {
      font-family: sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      background: #f4f4f4;
    }
    .container {
      width: 90%;
      max-width: 360px; /* ここを調整することで「半分サイズ」に */
      background: white;
      padding: 20px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      border-radius: 12px;
    }
    h1 {
      font-size: 1.4em;
      text-align: center;
      margin-bottom: 20px;
    }
    label {
      display: block;
      margin-top: 10px;
      font-weight: bold;
    }
    input, button {
      width: 100%;
      font-size: 1em;
      padding: 10px;
      margin-top: 5px;
      box-sizing: border-box;
    }
    #result {
      font-size: 1.3em;
      text-align: center;
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>塩分濃度計算</h1>

    <label>水の量（ml または g）</label>
    <input type="number" id="water" placeholder="例: 450">

    <label>塩の量（g）</label>
    <input type="number" id="salt" placeholder="例: 13">

    <button onclick="calc()">計算</button>

    <div id="result"></div>
  </div>

  <script>
    function calc() {
      const water = parseFloat(document.getElementById('water').value);
      const salt = parseFloat(document.getElementById('salt').value);
      if (isNaN(water) || isNaN(salt)) {
        document.getElementById('result').innerText = "数値を正しく入力してください。";
        return;
      }
      const total = water + salt;
      const percent = (salt / total) * 100;
      document.getElementById('result').innerText = "濃度: " + percent.toFixed(2) + " %";
    }
  </script>
</body>
</html>
