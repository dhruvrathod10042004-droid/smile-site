<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>A Little Smile For You 💛</title>

<style>
:root {
  --bg1:#f7e9ff;
  --bg2:#e6f7ff;
  --accent:#ffb6b9;
  --card:#ffffffcc;
  --text:#333;
}

body {
  margin:0;
  font-family: "Segoe UI", sans-serif;
  background: linear-gradient(120deg,var(--bg1),var(--bg2));
  color:var(--text);
  display:flex;
  flex-direction:column;
  align-items:center;
  min-height:100vh;
}

/* Layout */
header {
  text-align:center;
  padding:20px;
}

h1 {
  margin:5px;
}

.container {
  width:95%;
  max-width:800px;
}

.card {
  background:var(--card);
  backdrop-filter: blur(6px);
  border-radius:18px;
  padding:18px;
  margin:12px 0;
  box-shadow:0 4px 14px rgba(0,0,0,0.08);
}

/* Buttons */
button {
  background:var(--accent);
  border:none;
  border-radius:10px;
  padding:10px 16px;
  margin:6px;
  font-size:1rem;
  cursor:pointer;
}

button:hover {
  opacity:0.9;
}

/* Inputs */
textarea, input {
  width:100%;
  padding:8px;
  margin-top:8px;
  border-radius:8px;
  border:1px solid #ccc;
  font-size:1rem;
}

/* Quote text */
#quote {
  font-style:italic;
  margin-top:10px;
}

/* Simple game bubbles */
#bubble-area {
  position:relative;
  height:150px;
  overflow:hidden;
}

.bubble {
  position:absolute;
  bottom:-40px;
  width:35px;
  height:35px;
  border-radius:50%;
  background:rgba(255,255,255,0.8);
  animation:rise 6s linear forwards;
  cursor:pointer;
}

@keyframes rise {
  to {
    transform: translateY(-220px);
    opacity:0;
  }
}

/* Footer */
footer {
  margin-top:auto;
  padding:10px;
  font-size:0.85rem;
  opacity:0.6;
}
</style>
</head>

<body>

<header>
  <h1>Hey 🌼</h1>
  <p>This little space was made just to bring you a smile.</p>
</header>

<div class="container">

<!-- Personal message -->
<div class="card">
  <h2>💌 A Note</h2>
  <h3> "Tu sad rehgi tho kaise chalega SHAMPY...??!! 🐼 "</textarea>

  <p id="messageDisplay"></p>
</div>

<!-- Quotes -->
<div class="card">
  <h3>✨ Uplifting Thought</h3>
  <button onclick="newQuote()">Click to see a sweet message 💛 </button>
  <p id="quote"></p>
</div>



<!-- Memory customization -->
<div class="card">
  <h1>📸 Memory Corner</h1>
 <h3>"Sahi hai , jab sab sahi tha tab u shared every little thing , bedroom door k piche washroom banaya tha vho sab . aur ab 1 month hone aaya haal chal bhi ni pucha mera 😟"</h3>
  <p id="memoryDisplay"></p>
</div>

</div>

<footer>
  Everything here runs locally — nothing is stored or shared.
</footer>

<script>
/* Message */
function showMessage(){
  document.getElementById("messageDisplay").innerText =
    document.getElementById("messageInput").value;
}

/* Quotes */
const quotes = [
  "You are stronger than you think.",
  "It’s okay to pause — but not okay to  quit.",
  "Even cloudy days pass.",
  "You matter more than you realize.",
  "Small steps still move you forward."
];

function newQuote(){
  const q = quotes[Math.floor(Math.random()*quotes.length)];
  document.getElementById("quote").innerText = q;
}


/* Memory */
function saveMemory(){
  const text = document.getElementById("memoryText").value;
  localStorage.setItem("memory",text);
  document.getElementById("memoryDisplay").innerText=text;
}

window.onload = ()=>{
  const saved = localStorage.getItem("memory");
  if(saved) document.getElementById("memoryDisplay").innerText=saved;
}
</script>

</body>
</html>
