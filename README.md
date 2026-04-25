<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>SHEE GROUP</title>

<style>
body {
  text-align:center;
  font-family:Arial;
  background:#0B3C5D;
  color:white;
}

h1 { margin-top:20px; }

.card {
  background:white;
  color:black;
  margin:20px;
  padding:20px;
  border-radius:15px;
}

button {
  padding:15px;
  font-size:18px;
  margin:10px;
  border:none;
  border-radius:10px;
  cursor:pointer;
}

.red { background:red; color:white; }
.green { background:green; color:white; }

#timer { font-size:40px; }
</style>
</head>

<body>

<h1>SHEE GROUP</h1>

<div class="card">
<h2>Color Prediction Game</h2>
<h1 id="timer">30</h1>

<button class="red" onclick="choose('RED')">RED</button>
<button class="green" onclick="choose('GREEN')">GREEN</button>

<h3 id="result"></h3>
</div>

<script>
let time = 30;
let choice = "";

function choose(c){ choice = c; }

setInterval(()=>{
  time--;
  document.getElementById("timer").innerText = time;

  if(time == 0){
    let result = Math.random() > 0.5 ? "RED" : "GREEN";

    document.getElementById("result").innerText =
      (choice == result) ? "WIN 🎉" : "LOSE ❌";

    time = 30;
  }
},1000);
</script>

</body>
</html>
