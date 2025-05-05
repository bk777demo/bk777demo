<!DOCTYPE html><html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BK777 খেলার সাইট</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #e6f2ff;
            margin: 0;
            padding: 20px;
            text-align: center;
        }
        .container {
            background-color: #fff;
            padding: 25px;
            max-width: 420px;
            margin: auto;
            border-radius: 12px;
            box-shadow: 0 0 12px rgba(0,0,0,0.15);
        }
        h2 {
            color: #004080;
        }
        button {
            padding: 12px 20px;
            margin: 6px;
            font-size: 16px;
            cursor: pointer;
            border: none;
            background-color: #007bff;
            color: white;
            border-radius: 5px;
        }
        button:hover {
            background-color: #0056b3;
        }
        input, select {
            padding: 10px;
            margin: 10px 0;
            width: 90%;
            border: 1px solid #aaa;
            border-radius: 5px;
        }
        .result {
            margin-top: 15px;
            font-weight: bold;
            color: #006600;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>BK777 খেলার সাইট</h2>
        <p>আপনার পছন্দ বেছে নিন:</p>
        <button onclick="selectBet('Win')">জিতবে</button>
        <button onclick="selectBet('Loss')">হারবে</button>
        <button onclick="selectBet('Draw')">ড্র</button><p>আপনার নাম লিখুন:</p>
    <input type="text" id="username" placeholder="নাম">

    <p>পেমেন্ট অপশন:</p>
    <select id="payment">
        <option value="bkash">বিকাশ</option>
        <option value="nagad">নগদ</option>
        <option value="rocket">রকেট</option>
    </select>

    <p>টাকার পরিমাণ (৳):</p>
    <input type="number" id="amount" placeholder="৳ টাকার পরিমাণ">

    <div class="result" id="betResult"></div>
    <button onclick="submitBet()">সাবমিট বেট</button>

    <div class="result" id="finalResult"></div>
    <button onclick="showResult()">ফলাফল দেখুন</button>
</div>

<script>
    let chosenBet = '';

    function selectBet(option) {
        chosenBet = option;
    }

    function submitBet() {
        let name = document.getElementById('username').value.trim();
        let payment = document.getElementById('payment').value;
        let amount = document.getElementById('amount').value.trim();

        if (!name || !amount || !chosenBet) {
            alert('দয়া করে সব তথ্য পূরণ করুন ও একটি অপশন বেছে নিন।');
            return;
        }

        document.getElementById('betResult').innerText = `${name}, আপনি ${chosenBet} বেছে নিয়েছেন (৳${amount}, ${payment})।`;
        document.getElementById('finalResult').innerText = '';
    }

    function showResult() {
        if (!chosenBet) {
            alert('দয়া করে একটি বেট অপশন বেছে নিন।');
            return;
        }

        let results = ['Win', 'Loss', 'Draw'];
        let actual = results[Math.floor(Math.random() * results.length)];
        let message = (actual === chosenBet) ? 'অভিনন্দন! আপনি জিতেছেন!' : 'দুঃখিত, আপনি হারিয়েছেন।';

        document.getElementById('finalResult').innerText = `ফলাফল: ${actual} - ${message}`;
    }
</script>

</body>
</html>
