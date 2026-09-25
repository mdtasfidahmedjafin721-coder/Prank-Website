<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Security Alert 😈</title>
<style>
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
  }
  .box {
    width: 85%;
    padding: 25px;
    border: 2px solid #ff3333;
    border-radius: 15px;
    box-shadow: 0 0 25px #ff3333;
  }
  .icon { font-size: 55px; }
  h1 { color: #ff4444; }
  button {
    background: #ff3333;
    color: white;
    border: 0;
    padding: 13px 25px;
    border-radius: 8px;
    font-size: 16px;
  }
</style>
</head>

<body>
<div class="box">
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

function reveal() {
  document.querySelector(".box").innerHTML = `
    <div class="icon">😈</div>
    <h1>PRANK!</h1>
    <p>তোমার ফোন হ্যাক হয়েছে</p>
    <p>বাচঁতে চাইলে জাফিনের সাথে ভালো ব্যবহার করো 😈</p>
  `;
}
</script>

</body>
</html>
