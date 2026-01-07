# Name-<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>What Does Your Name Say About You?</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
  background: #f7c6cc;
  font-family: Arial, sans-serif;
  text-align: center;
}

.box {
  background: #fff6e8;
  width: 90%;
  max-width: 400px;
  margin: 60px auto;
  padding: 20px;
  border-radius: 12px;
}

input {
  padding: 10px;
  width: 80%;
  font-size: 16px;
}

button {
  padding: 10px 25px;
  background: #9ad0e6;
  border: none;
  border-radius: 20px;
  font-size: 16px;
  cursor: pointer;
  margin-top: 10px;
}

#shareBtn {
  display: none;
  background: #25D366;
  color: white;
}
</style>
</head>

<body>

<div class="box">
  <h2>WHAT DOES YOUR NAME SAY ABOUT YOU?</h2>
  <p>Enter your name and see your personality</p>

  <input type="text" id="name" placeholder="Enter your name">
  <br><br>

  <button onclick="showResult()">SUBMIT</button>

  <h3 id="result"></h3>

  <button id="shareBtn" onclick="shareWhatsApp()">Share on WhatsApp</button>
</div>

<script>
function showResult() {
  let name = document.getElementById("name").value;

  if (name === "") {
    alert("Please enter your name");
    return;
  }

  let messages = [
    "you are strong-minded and never give up 💪",
    "you are intelligent and people respect you 🧠",
    "you are calm and wise 🌱",
    "you are ambitious and destined for success 🔥",
    "you are kind-hearted and trustworthy ❤️",
    "you are creative and full of ideas 🎨",
    "you are a natural leader 👑",
    "you are confident and bold 😎"
  ];

  let index = name.length % messages.length;

  document.getElementById("result").innerText =
    name + ", " + messages[index];

  document.getElementById("shareBtn").style.display = "inline-block";
}

function shareWhatsApp() {
  let result = document.getElementById("result").innerText;
  let url = window.location.href;
  let text = encodeURIComponent(result + "\n\nTry yours here 👉 " + url);
  window.open("https://wa.me/?text=" + text, "_blank");
}
</script>

</body>
</html>
