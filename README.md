<!DOCTYPE html>
<html lang="sq">
<head>
<meta charset="UTF-8">
<title>BASTEFIER – Sports Betting</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body{margin:0;font-family:Arial,Helvetica,sans-serif;background:#0b132b;color:#fff}
header{background:#1c2541;padding:15px;text-align:center}
header h1{margin:0;color:#5bc0be;letter-spacing:2px}
nav{display:flex;justify-content:center;gap:15px;background:#3a506b;padding:10px;flex-wrap:wrap}
nav a{color:#fff;text-decoration:none;font-weight:bold}
nav a:hover{color:#5bc0be}
.container{display:flex;flex-wrap:wrap;padding:15px}
.matches{flex:3;min-width:260px}
.bet-slip{flex:1;min-width:260px;background:#1c2541;padding:15px;margin-left:10px;border-radius:8px}
.match{background:#1c2541;margin-bottom:10px;padding:10px;border-radius:8px}
.match h3{margin-top:0}
.odds button{margin:5px;padding:8px 12px;border:none;border-radius:5px;background:#3a506b;color:#fff;cursor:pointer}
.odds button:hover{background:#5bc0be;color:#000}
.bet-slip h3{text-align:center;margin-top:0}
input{width:100%;padding:8px;margin-top:8px;border-radius:5px;border:none}
.btn{background:#5bc0be;color:#000;padding:10px;border:none;width:100%;margin-top:10px;border-radius:5px;font-weight:bold}
footer{text-align:center;background:#1c2541;padding:10px;font-size:13px;color:#aaa}
ul{padding-left:18px}
</style>
</head>

<body>

<header>
  <h1>BASTEFIER</h1>
  <p>Baste sportive • Live • Demo Platform</p>
</header>

<nav>
  <a href="#">Futboll</a>
  <a href="#">Basketboll</a>
  <a href="#">Tenis</a>
  <a href="#">Live</a>
  <a href="#">Login</a>
</nav>

<div class="container">
  <div class="matches">

    <div class="match">
      <h3>Real Madrid vs Barcelona</h3>
      <div class="odds">
        <button onclick="addBet('Real Madrid',1.85)">1 1.85</button>
        <button onclick="addBet('Barazim',3.40)">X 3.40</button>
        <button onclick="addBet('Barcelona',2.10)">2 2.10</button>
      </div>
    </div>

    <div class="match">
      <h3>Manchester City vs Arsenal</h3>
      <div class="odds">
        <button onclick="addBet('Man City',1.70)">1 1.70</button>
        <button onclick="addBet('Barazim',3.60)">X 3.60</button>
        <button onclick="addBet('Arsenal',2.30)">2 2.30</button>
      </div>
    </div>

    <div class="match">
      <h3>Juventus vs Milan</h3>
      <div class="odds">
        <button onclick="addBet('Juventus',2.00)">1 2.00</button>
        <button onclick="addBet('Barazim',3.20)">X 3.20</button>
        <button onclick="addBet('Milan',2.90)">2 2.90</button>
      </div>
    </div>

  </div>

  <div class="bet-slip">
    <h3>BILETA</h3>
    <ul id="slip"></ul>
    <p>Koeficient total: <strong><span id="total">1.00</span></strong></p>
    <input type="number" id="stake" placeholder="Shuma €">
    <button class="btn" onclick="placeBet()">Luaj (DEMO)</button>
    <p id="win"></p>
  </div>
</div>

<footer>
  © 2026 BASTEFIER • DEMO • +18 • Luaj me përgjegjësi
</footer>

<script>
let total = 1;

function addBet(name, odd){
  total *= odd;
  document.getElementById("total").innerText = total.toFixed(2);
  let li = document.createElement("li");
  li.innerText = name + " @" + odd;
  document.getElementById("slip").appendChild(li);
}

function placeBet(){
  let stake = document.getElementById("stake").value || 0;
  document.getElementById("win").innerText =
    "Fitim i mundshëm: " + (stake * total).toFixed(2) + " € (DEMO)";
}
</script>

</body>
</html>
