<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Security Alert 😈</title>

<style>
  * {
    box-sizing: border-box;
  }

  body {
    margin: 0;
    background: #080808;
    color: white;
    font-family: Arial, sans-serif;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    text-align: center;
    overflow: hidden;
  }

  .box {
    width: 85%;
    padding: 25px;
    border: 2px solid #ff3333;
    border-radius: 15px;
    box-shadow: 0 0 25px #ff3333;
    animation: shake 0.08s infinite;
  }

  .icon {
    font-size: 55px;
  }

  h1 {
    color: #ff4444;
    animation: glitch 0.18s infinite;
  }

  p {
    font-size: 18px;
  }

  button {
    background: #ff3333;
    color: white;
    border: 0;
    padding: 13px 25px;
    border-radius: 8px;
    font-size: 16px;
    cursor: pointer;
  }

  button:hover {
    background: #ff0000;
  }

  .glitch {
    animation: glitch 0.1s infinite;
  }

  @keyframes shake {
    0%   { transform: translate(0, 0) rotate(0deg); }
    25%  { transform: translate(3px, -2px) rotate(-1deg); }
    50%  { transform: translate(-3px, 2px) rotate(1deg); }
    75%  { transform: translate(2px, 3px) rotate(0deg); }
    100% { transform: translate(-2px, -3px) rotate(-1deg); }
  }

  @keyframes glitch {
    0% { transform: translate(0); text-shadow: 2px 0 red, -2px 0 cyan; }
    25% { transform: translate(-3px, 2px); }
    50% { transform: translate(3px, -2px); text-shadow: -2px 0 red, 2px 0 cyan; }
    75% { transform: translate(2px, 1px); }
    100% { transform: translate(0); }
  }

  .flash {
    animation: flash 0.12s infinite;
  }

  @keyframes flash {
    50% {
      background: #300000;
    }
  }
</style>
</head>

<body>

<div class="box" id="box">
  <div class="icon">⚠️</div>

  <h1>SECURITY ALERT</h1>

  <p>অস্বাভাবিক কার্যকলাপ শনাক্ত হয়েছে!</p>

  <p id="status">Checking device...</p>

  <button onclick="reveal()">Check Result</button>
</div>

<script>
setTimeout(() => {
  document.getElementById("status").innerText =
    "Device scan completed...";
}, 2500);

function alarm() {
  const AudioContext = window.AudioContext || window.webkitAudioContext;
  const ctx = new AudioContext();

  let count = 0;

  const interval = setInterval(() => {
    const osc = ctx.createOscillator();
    const gain = ctx.createGain();

    osc.type = "square";
    osc.frequency.value = count % 2 === 0 ? 900 : 500;

    gain.gain.value = 0.12;

    osc.connect(gain);
    gain.connect(ctx.destination);

    osc.start();
    osc.stop(ctx.currentTime + 0.16);

    count++;

    if (count >= 12) {
      clearInterval(interval);
      setTimeout(() => ctx.close(), 300);
    }
  }, 220);
}

function reveal() {
  alarm();

  document.body.classList.add("flash");

  document.getElementById("box").innerHTML = `
    <div class="icon glitch">👿</div>

    <h1 class="glitch">PRANK!</h1>

    <p class="glitch">Your phone has been hacked. 👀</p>

    <p class="glitch">
      If you want to survive, treat Jafin nicely! 😈
    </p>

    <p>😈 Just kidding! It's only a harmless prank.</p>
  `;
}
</script>

</body>
</html>
