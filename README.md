<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>EarnTrack - صيد الهميزات</title>
    <style>
        body { font-family: sans-serif; text-align: center; background: #f4f4f4; padding: 20px; }
        .container { background: white; padding: 20px; border-radius: 15px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); max-width: 800px; margin: auto; }
        table { width: 100%; border-collapse: collapse; margin-top: 20px; }
        th, td { border: 1px solid #ddd; padding: 12px; text-align: center; }
        th { background: #2ecc71; color: white; }
        .pay-btn { background: #f1c40f; border: none; padding: 8px 15px; border-radius: 5px; cursor: pointer; font-weight: bold; }
    </style>
</head>
<body>
    <div class="container">
        <h1>🚀 EarnTrack: رادار الهميزات</h1>
        <table>
            <thead>
                <tr>
                    <th>الفرصة</th>
                    <th>الربح المتوقع</th>
                    <th>الرابط</th>
                </tr>
            </thead>
            <tbody id="data-list">
                <tr>
                    <td>Airdrop عملة جديدة (مأكد)</td>
                    <td>$25</td>
                    <td><button class="pay-btn" onclick="showPay()">فتح بـ $1</button></td>
                </tr>
            </tbody>
        </table>
        <div id="paypal-container" style="margin-top:20px; display:none;">
            <div id="paypal-button-container"></div>
        </div>
    </div>

    <script src="https://www.paypal.com/sdk/js?client-id=sb&currency=USD"></script>
    <script>
        function showPay() { document.getElementById('paypal-container').style.display = 'block'; }
        paypal.Buttons({
            createOrder: (data, actions) => actions.order.create({ purchase_units: [{ amount: { value: '1.00' } }] }),
            onApprove: (data, actions) => actions.order.capture().then(details => alert('تم الخلاص! الرابط هو: www.airdrop-link.com'))
        }).render('#paypal-button-container');
    </script>
</body>
</html>
