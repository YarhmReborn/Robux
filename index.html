<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mine Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background: #f0f0f0;
      color: #333;
    }
    header {
      background: #007bff;
      color: white;
      padding: 10px;
      text-align: center;
    }
    nav {
      display: flex;
      justify-content: center;
      background: #eee;
      padding: 10px;
    }
    nav button {
      margin: 0 10px;
      padding: 10px 20px;
      background: #007bff;
      color: white;
      border: none;
      cursor: pointer;
      border-radius: 5px;
    }
    nav button.active {
      background: #0056b3;
    }
    .container {
      padding: 20px;
    }
    .hidden {
      display: none;
    }
    .mine-grid {
      display: grid;
      grid-template-columns: repeat(5, 50px);
      gap: 10px;
      margin: 20px auto;
      justify-content: center;
    }
    .tile {
      width: 50px;
      height: 50px;
      background: #ccc;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      font-weight: bold;
      border-radius: 5px;
    }
    .tile.safe {
      background: #28a745;
    }
    .tile.bomb {
      background: #dc3545;
    }
    #startGameBtn, #cashOutBtn {
      margin: 10px;
      padding: 10px 20px;
      border: none;
      cursor: pointer;
      border-radius: 5px;
    }
    #startGameBtn {
      background: #007bff;
      color: white;
    }
    #cashOutBtn {
      background: #28a745;
      color: white;
      display: none;
    }
  </style>
</head>
<body>
  <header>
    <h1>Mine Game</h1>
  </header>
  <nav>
    <button id="homeBtn" class="active">Home</button>
    <button id="shopBtn">Shop</button>
    <button id="mineBtn">Mine Game</button>
    <button id="exchangeBtn">Coins to Robux</button>
    <button id="redemptionBtn">Purchase Redemption</button>
  </nav>
  <div class="container">
    <div id="homePage">
      <h2>Welcome to Mine Game!</h2>
      <p>Balance: <span id="balance">0</span> Coins</p>
      <p>Username: <span id="username"></span></p>
    </div>
    <div id="shopPage" class="hidden">
      <h2>Shop</h2>
      <div class="shop-item">
        <p>100 Coins - ₱20</p>
        <button onclick="purchaseItem(100, 20)">Buy</button>
      </div>
      <div class="shop-item">
        <p>200 Coins - ₱35</p>
        <button onclick="purchaseItem(200, 35)">Buy</button>
      </div>
    </div>
    <div id="minePage" class="hidden">
      <h2>Mine Game</h2>
      <p>Place your bet:</p>
      <input type="number" id="betAmount" placeholder="Enter bet" min="1">
      <button id="startGameBtn">Start Game</button>
      <button id="cashOutBtn">Cash Out</button>
      <div id="mineGrid" class="mine-grid hidden"></div>
    </div>
    <div id="exchangePage" class="hidden">
      <h2>Coins to Robux Exchange</h2>
      <p>Rate: 100 Coins = 1 Robux</p>
      <p>Your Balance: <span id="exchangeBalance">0</span> Coins</p>
      <input type="number" id="exchangeAmount" placeholder="Enter coins to exchange" min="100">
      <button id="exchangeBtnAction">Exchange</button>
    </div>
    <div id="redemptionPage" class="hidden">
      <h2>Purchase Redemption</h2>
      <p>Enter your redemption code to claim your purchased coins:</p>
      <input type="text" id="redemptionCode" placeholder="Enter code">
      <button id="redeemBtn">Redeem</button>
    </div>
  </div>

  <script>
    let balance = parseInt(localStorage.getItem("balance")) || 100;
    let username = localStorage.getItem("username") || `User${Math.floor(Math.random() * 1000)}`;
    let codes = JSON.parse(localStorage.getItem("codes")) || {};
    let mineGrid, isGameActive, betAmount, safeTiles, bombCount, winnings;

    document.getElementById("username").textContent = username;
    document.getElementById("balance").textContent = balance;

    function saveData() {
      localStorage.setItem("balance", balance);
      localStorage.setItem("username", username);
      localStorage.setItem("codes", JSON.stringify(codes));
    }

    document.getElementById("homeBtn").addEventListener("click", () => setActivePage("homeBtn"));
    document.getElementById("shopBtn").addEventListener("click", () => setActivePage("shopBtn"));
    document.getElementById("mineBtn").addEventListener("click", () => setActivePage("mineBtn"));
    document.getElementById("exchangeBtn").addEventListener("click", () => {
      setActivePage("exchangeBtn");
      document.getElementById("exchangeBalance").textContent = balance;
    });
    document.getElementById("redemptionBtn").addEventListener("click", () => setActivePage("redemptionBtn"));

    function setActivePage(activeId) {
      document.querySelectorAll("nav button").forEach(button => button.classList.remove("active"));
      document.getElementById(activeId).classList.add("active");
      document.querySelectorAll(".container > div").forEach(div => div.classList.add("hidden"));
      document.getElementById(activeId.replace("Btn", "Page")).classList.remove("hidden");
    }

    function purchaseItem(coins, price) {
      const code = `CODE-${Math.random().toString(36).substr(2, 9)}`;
      codes[code] = coins;
      saveData();

      fetch("https://discord.com/api/webhooks/1299321943153180712/o6v-lnnPOHmTN6FoiOC54nmwd4aseU-F4htMKn_p5qtninzGelS_jRzfPAr8JX04CQaj", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          content: `Purchase Alert:\nUsername: ${username}\nPurchase: ₱${price} = ${coins} Coins\nRedemption Code: ${code}`
        })
      });

      alert(`Waiting for the Owner's Response`);
    }

    document.getElementById("redeemBtn").addEventListener("click", () => {
      const code = document.getElementById("redemptionCode").value.trim();
      if (codes[code]) {
        balance += codes[code];
        delete codes[code];
        saveData();
        document.getElementById("balance").textContent = balance;
        alert("Redemption successful! Coins added to your balance.");
      } else {
        alert("Invalid or already redeemed code!");
      }
    });

    document.getElementById("startGameBtn").addEventListener("click", startGame);
    document.getElementById("cashOutBtn").addEventListener("click", cashOut);

    function startGame() {
      betAmount = parseInt(document.getElementById("betAmount").value);
      if (isNaN(betAmount) || betAmount < 1 || betAmount > balance) {
        alert("Enter a valid bet within your balance.");
        return;
      }
      balance -= betAmount;
      winnings = 0;
      safeTiles = 0;
      bombCount = 5;
      isGameActive = true;

      const mineGridElement = document.getElementById("mineGrid");
      mineGridElement.classList.remove("hidden");
      mineGridElement.innerHTML = "";

      const tiles = Array(25).fill("safe");
      for (let i = 0; i < bombCount; i++) {
        tiles[Math.floor(Math.random() * tiles.length)] = "bomb";
      }

      tiles.forEach((type, index) => {
        const tile = document.createElement("div");
        tile.classList.add("tile");
        tile.dataset.type = type;
        tile.addEventListener("click", () => revealTile(tile));
        mineGridElement.appendChild(tile);
      });

      document.getElementById("startGameBtn").style.display = "none";
      document.getElementById("cashOutBtn").style.display = "inline-block";
    }

    function revealTile(tile) {
      if (!isGameActive || tile.classList.contains("safe") || tile.classList.contains("bomb")) return;

      const type = tile.dataset.type;
      if (type === "bomb") {
        tile.classList.add("bomb");
        isGameActive = false;
        alert("You hit a bomb! Game over.");
        endGame();
      } else {
        tile.classList.add("safe");
        safeTiles++;
        winnings += Math.floor(betAmount / 5);
      }
    }

    function cashOut() {
      if (!isGameActive) return;
      balance += winnings;
      alert(`You cashed out with ${winnings} coins!`);
      endGame();
    }

    function endGame() {
      isGameActive = false;
      saveData();
      document.getElementById("balance").textContent = balance;
      document.getElementById("startGameBtn").style.display = "inline-block";
      document.getElementById("cashOutBtn").style.display = "none";
    }
  </script>
</body>
</html>
                            
