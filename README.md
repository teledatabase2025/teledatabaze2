<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Můj web</title>
</head>
<body>

<h1>Vyhledávání měst</h1>

<input type="text" id="userInput" placeholder="Zadej město">
<button onclick="go()">OK</button>

<script>
function normalizeText(text) {
  return text
    .trim()
    .toLowerCase()
    .normalize("NFD")
    .replace(/[\u0300-\u036f]/g, "");
}

function go() {
  const val = normalizeText(document.getElementById("userInput").value);

  const pages = {
    "praha": "praha.html",
    "brno": "brno.html",
    "ostrava": "ostrava.html"
  };

  if (pages[val]) {
    window.location.href = pages[val];
  } else {
    alert("Neznámé město");
  }
}
</script>

<hr>

<p>Klikací verze:</p>
<a href="praha.html">Praha</a> |
<a href="brno.html">Brno</a> |
<a href="ostrava.html">Ostrava</a>

</body>
</html>
