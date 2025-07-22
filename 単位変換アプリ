<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>単位変換アプリ</title>
    <style>
        body {
            font-family: sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f2f5;
        }
        .converter {
            background: white;
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            text-align: center;
        }
        h1 {
            margin-bottom: 1.5rem;
        }
        .input-group {
            margin-bottom: 1rem;
        }
        input, select {
            padding: 0.5rem;
            font-size: 1rem;
            border-radius: 4px;
            border: 1px solid #ccc;
        }
        .result {
            margin-top: 1.5rem;
            font-size: 1.2rem;
            font-weight: bold;
        }
    </style>
</head>
<body>

<div class="converter">
    <h1>単位変換</h1>
    <div class="input-group">
        <input type="number" id="inputValue" placeholder="値を入力...">
        <select id="fromUnit">
            <option value="meters">メートル</option>
            <option value="feet">フィート</option>
        </select>
    </div>
    <p>↓</p>
    <div class="input-group">
        <select id="toUnit">
            <option value="feet">フィート</option>
            <option value="meters">メートル</option>
        </select>
    </div>
    <button onclick="convert()">変換</button>
    <div class="result" id="result"></div>
</div>

<script>
    function convert() {
        const inputValue = document.getElementById('inputValue').value;
        const fromUnit = document.getElementById('fromUnit').value;
        const toUnit = document.getElementById('toUnit').value;
        const resultElement = document.getElementById('result');

        if (inputValue === '') {
            resultElement.innerText = '数値を入力してください';
            return;
        }

        let result;
        const value = parseFloat(inputValue);

        // メートルからフィートへ
        if (fromUnit === 'meters' && toUnit === 'feet') {
            result = value * 3.28084;
        } 
        // フィートからメートルへ
        else if (fromUnit === 'feet' && toUnit === 'meters') {
            result = value / 3.28084;
        } 
        // 同じ単位同士
        else {
            result = value;
        }

        resultElement.innerText = `${result.toFixed(3)} ${toUnit}`;
    }
</script>

</body>
</html>
