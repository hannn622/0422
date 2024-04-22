<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>貨幣轉換器：台幣與日幣</title>
    <script>
        function convertCurrency() {
            var amount = document.getElementById('amount').value;
            var fromCurrency = document.getElementById('fromCurrency').value;
            var toCurrency = document.getElementById('toCurrency').value;
            var result = 0;
            var rateTWDToJPY = 4; // 假設1台幣兌換4日幣，實際匯率請參考最新數據
            var rateJPYToTWD = 0.25; // 假設1日幣兌換0.25台幣，實際匯率請參考最新數據

            if (fromCurrency === 'TWD' && toCurrency === 'JPY') {
                result = amount * rateTWDToJPY;
            } else if (fromCurrency === 'JPY' && toCurrency === 'TWD') {
                result = amount * rateJPYToTWD;
            } else {
                result = amount; // 同幣種轉換，金額不變
            }

            document.getElementById('result').innerText = `轉換結果：${result.toFixed(2)} ${toCurrency}`;
        }
    </script>
</head>
<body>
    <h1>台幣與日幣轉換器</h1>
    <div>
        <label for="amount">輸入金額：</label>
        <input type="number" id="amount" placeholder="輸入金額">
    </div>
    <div>
        <label for="fromCurrency">原始貨幣：</label>
        <select id="fromCurrency">
            <option value="TWD">台幣 (TWD)</option>
            <option value="JPY">日幣 (JPY)</option>
        </select>
    </div>
    <div>
        <label for="toCurrency">目標貨幣：</label>
        <select id="toCurrency">
            <option value="JPY">日幣 (JPY)</option>
            <option value="TWD">台幣 (TWD)</option>
        </select>
    </div>
    <button onclick="convertCurrency()">轉換</button>
    <div id="result"></div>
</body>
</html>
