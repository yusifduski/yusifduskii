<!DOCTYPE html>
<html lang="ku">
<head>
    <meta charset="UTF-8">
    <title>Pro Gyro Settings | PUBG</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            background: linear-gradient(135deg, #0a0f1e 0%, #0f172a 100%);
            color: white;
            font-family: system-ui;
            direction: rtl;
            padding: 20px;
        }
        h1 { text-align: center; color: #a855f7; margin-bottom: 30px; }
        .card {
            background: rgba(255,255,255,0.1);
            border-radius: 20px;
            padding: 20px;
            margin-bottom: 20px;
        }
        .price { color: #facc15; font-size: 28px; font-weight: bold; }
        button {
            background: #a855f7;
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 40px;
            font-size: 16px;
            margin-top: 10px;
        }
        input, select {
            width: 100%;
            padding: 12px;
            margin: 8px 0;
            border-radius: 12px;
            border: none;
        }
        .success { background: #10b981; padding: 10px; border-radius: 12px; display: none; margin-top: 15px; }
    </style>
</head>
<body>
    <h1>🎯 Pro Gyro Settings</h1>
    <p style="text-align:center;">باشترین ستینگەکانی فول جايرۆ بۆ iPhone 13 Pro Max</p>

    <div class="card">
        <h3>📱 ستینگەکان</h3>
        <div class="price">$10</div>
        <button onclick="selectPackage('ستینگەکان', 10)">بکڕە</button>
    </div>

    <div class="card">
        <h3>🎯 ستینگ + ڕاهێنان</h3>
        <div class="price">$25</div>
        <button onclick="selectPackage('ستینگ + ڕاهێنان', 25)">بکڕە</button>
    </div>

    <div id="orderForm" style="margin-top: 30px;">
        <h3>📝 فۆرمی داواکاری</h3>
        <input type="text" id="fullName" placeholder="ناوی تەواو">
        <input type="tel" id="phone" placeholder="ژمارەی مۆبایل">
        <select id="packageSelect">
            <option>ستینگەکان - $10</option>
            <option>ستینگ + ڕاهێنان - $25</option>
        </select>
        <button onclick="sendOrder()">ناردن</button>
        <div id="successMsg" class="success">✅ نێردرا!</div>
    </div>

    <script>
        function selectPackage(name, price) {
            document.getElementById('packageSelect').value = name + ' - $' + price;
            document.getElementById('orderForm').scrollIntoView({ behavior: 'smooth' });
        }
        function sendOrder() {
            const name = document.getElementById('fullName').value;
            const phone = document.getElementById('phone').value;
            const pkg = document.getElementById('packageSelect').value;
            const msg = `داواکاری نوێ: ${pkg}\nناو: ${name}\nمۆبایل: ${phone}`;
            window.open(`https://wa.me/964770000000?text=${encodeURIComponent(msg)}`, '_blank');
            document.getElementById('successMsg').style.display = 'block';
            setTimeout(() => { document.getElementById('successMsg').style.display = 'none'; }, 3000);
        }
    </script>
    <p style="text-align:center; margin-top:30px;">© 2025 Pro Gyro Settings</p>
</body>
</html>
