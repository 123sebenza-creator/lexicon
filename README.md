<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lexicon - The Smart Scrambled Word Processor</title>

<style>
body {
font-family: Arial, sans-serif;
margin: 0;
background: #f8f9fb;
color: #333;
}

nav {
background: white;
padding: 1rem;
display: flex;
justify-content: space-between;
box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

nav h1 {
margin: 0;
color: #333;
}

.menu a {
margin-left: 15px;
text-decoration: none;
color: #555;
}

.hero {
text-align: center;
padding: 2rem;
}

.input-box {
text-align: center;
margin: 2rem;
}

input {
padding: 10px;
width: 250px;
font-size: 16px;
}

button {
padding: 10px 15px;
background: royalblue;
color: white;
border: none;
cursor: pointer;
}

.results {
text-align: center;
margin-top: 1rem;
}

.card {
background: white;
padding: 1rem;
margin: 1rem auto;
max-width: 500px;
box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

footer {
text-align: center;
padding: 1rem;
margin-top: 2rem;
}
</style>
</head>

<body>

<nav>
<h1>✨ Lexicon</h1>
<div class="menu">
<a href="#home">Home</a>
<a href="#dictionary">Dictionary</a>
<a href="#quotes">Motivation</a>
<a href="#gratitude">Gratitude</a>
<a href="#disclaimer">Disclaimer</a>
</div>
</nav>

<div class="hero" id="home">
<h2>The Smart Scrambled Word Processor</h2>
<p>Helping you learn, grow, and have fun by unscrambling words and improving your vocabulary.</p>
</div>

<div class="input-box">
<input type="text" id="letters" placeholder="Enter letters">
<button onclick="unscramble()">Unscramble</button>
<button onclick="startVoice()">🎤 Speak</button>
</div>

<div class="results" id="results"></div>

<div class="card" id="dictionary">
<h3>📘 Dictionary</h3>
<p>This tool uses a built-in word list to help generate meaningful words for learning and fun.</p>
</div>

<div class="card" id="quotes">
<h3>💡 Motivation</h3>
<ul>
<li>Keep going, your breakthrough is near.</li>
<li>You are stronger than you think.</li>
<li>Small steps lead to big success.</li>
<li>Growth happens daily.</li>
<li>Stay focused and never quit.</li>
<li>You are capable of greatness.</li>
<li>Believe in yourself always.</li>
<li>Success starts with effort.</li>
<li>Your future is bright.</li>
<li>Keep learning and rising.</li>
</ul>
</div>

<div class="card" id="gratitude">
<h3>🙏 Gratitude</h3>
<p>We are grateful for every user who chooses to grow and learn with Lexicon.</p>
</div>

<div class="card" id="disclaimer">
<h3>⚖ Disclaimer</h3>
<p>This site is for educational and entertainment purposes. Safe for school students. No personal data is collected.</p>
</div>

<footer>
<p>© 2026 Lexicon | Safe • Educational • Fun</p>
</footer>

<script>
const dictionary = ["cat","dog","bat","tab","act","god","tac"];

function unscramble() {
let input = document.getElementById("letters").value.toLowerCase();
let result = [];

dictionary.forEach(word => {
let sortedWord = word.split('').sort().join('');
let sortedInput = input.split('').sort().join('');
if (sortedInput.includes(sortedWord)) {
result.push(word);
}
});

document.getElementById("results").innerHTML = result.length
? "Results: " + result.join(", ")
: "No words found";
}

function startVoice() {
let recognition = new webkitSpeechRecognition();
recognition.onresult = function(event) {
document.getElementById("letters").value = event.results[0][0].transcript;
};
recognition.start();
}
</script>

</body>
</html>
