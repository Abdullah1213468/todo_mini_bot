<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Easy Earning Bot</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      background-color: #0f172a;
      color: white;
      font-family: sans-serif;
      margin: 0;
      padding: 0;
    }

    .container {
      max-width: 400px;
      margin: 2rem auto;
      padding: 1rem;
    }

    .card {
      background-color: #1e293b;
      border-radius: 1rem;
      padding: 1rem;
      margin-bottom: 1.5rem;
      text-align: center;
    }

    .title {
      font-size: 1.5rem;
      font-weight: bold;
      text-align: center;
      margin-bottom: 1rem;
    }

    .balance {
      font-size: 2rem;
      font-weight: bold;
    }

    .points {
      color: #facc15;
      margin-top: 0.5rem;
    }

    button {
      display: block;
      width: 100%;
      padding: 0.75rem;
      font-size: 1rem;
      font-weight: bold;
      margin-top: 1rem;
      border: none;
      border-radius: 0.75rem;
      cursor: pointer;
    }

    .btn-green {
      background-color: #10b981;
      color: white;
    }

    .btn-blue {
      background-color: #3b82f6;
      color: white;
    }

    .btn-gray {
      background-color: #4b5563;
      color: white;
    }

    .footer {
      text-align: center;
      font-size: 0.85rem;
      margin-top: 2rem;
      color: #9ca3af;
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="title">Easy Earning Bot</div>

    <div class="card">
      <div>Welcome Back!</div>
      <div class="balance" id="balance">$1.30</div>
      <div class="points">💰 <span id="points">26</span> Points</div>
    </div>

    <button class="btn btn-green" onclick="watchAd('interstitial')">Watch Fullscreen Ad</button>
    <button class="btn btn-blue" onclick="watchAd('popup')">Watch Popup Ad</button>
    <button class="btn btn-gray" onclick="withdraw()">Withdraw Funds</button>

    <div class="footer">Earn by watching ads. Withdraw when balance ≥ $1.</div>

    <!-- Interstitial Ad Container -->
    <div id="container-9626375" style="margin-top: 20px;"></div>
  </div>

  <script>
    let balance = 1.30;
    let points = 26;

    function updateUI() {
      document.getElementById("balance").textContent = "$" + balance.toFixed(2);
      document.getElementById("points").textContent = points;
    }

    function watchAd(type) {
      if (type === "interstitial") {
        alert("📺 Showing fullscreen ad...");

        // Make sure script isn't already loaded
        if (!document.getElementById("adscript")) {
          let script = document.createElement('script');
          script.id = "adscript";
          script.type = 'text/javascript';
          script.src = '//www.profitabledisplaynetwork.com/9626375/invoke.js';
          document.body.appendChild(script);
        }

        points += 2;
        balance += 0.10;

      } else if (type === "popup") {
        alert("📺 Opening popup ad...");
        window.open("https://www.profitabledisplaynetwork.com/9626375", "_blank");

        points += 1;
        balance += 0.05;
      }

      updateUI();
    }

    function withdraw() {
      if (balance >= 1.00) {
        alert("✅ Withdrawal Requested!");
        balance = 0;
        points = 0;
      } else {
        alert("❌ Minimum $1 required to withdraw.");
      }
      updateUI();
    }

    updateUI();
  </script>
</body>
</html>
