<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<title>Lanches Meirinha</title>
<style>
body {
  font-family: Arial;
  padding: 20px;
}

h2 {
  margin-top: 30px;
}

.item {
  border: 1px solid #ccc;
  padding: 10px;
  margin-bottom: 10px;
}

button {
  padding: 10px;
  margin-top: 10px;
}
</style>
</head>

<body>

<h1>Lanches Meirinha</h1>

<!-- PASTÉIS -->
<h2>Pastéis</h2>

<div class="item">
  <strong>24 cm - R$ 10,00</strong><br>

  Adicionais:<br>
  <input type="checkbox" value="Queijo"> Queijo<br>
  <input type="checkbox" value="Presunto"> Presunto<br>

  <br>Quantidade:
  <input type="number" min="1" value="1" id="qtdPastel">

  <br><button onclick="enviarPastel()">Pedir</button>
</div>

<!-- PRATINHOS -->
<h2>Pratinhos</h2>

<div class="item">
  <strong>Pratinho - R$ 12,00</strong><br>

  Adicionais:<br>
  <input type="checkbox" value="Queijo"> Queijo<br>
  <input type="checkbox" value="Presunto"> Presunto<br>
  <input type="checkbox" value="Ovo"> Ovo<br>

  <br>Quantidade:
  <input type="number" min="1" value="1" id="qtdPratinho">

  <br><button onclick="enviarPratinho()">Pedir</button>
</div>

<!-- BATATINHAS -->
<h2>Batatinhas</h2>

<div class="item">
  <strong>Batata - R$ 8,00</strong><br>

  Adicionais:<br>
  <input type="checkbox" value="Queijo"> Queijo<br>
  <input type="checkbox" value="Bacon"> Bacon<br>
  <input type="checkbox" value="Catupiry"> Catupiry<br>

  <br>Quantidade:
  <input type="number" min="1" value="1" id="qtdBatata">

  <br><button onclick="enviarBatata()">Pedir</button>
</div>

<script>

function pegarAdicionais(elemento) {
  let adicionais = [];
  let checks = elemento.parentElement.querySelectorAll('input[type="checkbox"]:checked');

  checks.forEach(c => adicionais.push(c.value));

  return adicionais.length > 0 ? adicionais.join(", ") : "Nenhum";
}

// Pastel
function enviarPastel() {
  let qtd = document.getElementById("qtdPastel").value;
  let adicionais = pegarAdicionais(event.target);

  let msg = `Pedido:%0A- Pastel 24 centímetros%0AQuantidade: ${qtd}%0AAdicionais: ${adicionais}`;
  abrirWhats(msg);
}

// Pratinho
function enviarPratinho() {
  let qtd = document.getElementById("qtdPratinho").value;
  let adicionais = pegarAdicionais(event.target);

  let msg = `Pedido:%0A- Pratinho%0AQuantidade: ${qtd}%0AAdicionais: ${adicionais}`;
  abrirWhats(msg);
}

// Batata
function enviarBatata() {
  let qtd = document.getElementById("qtdBatata").value;
  let adicionais = pegarAdicionais(event.target);

  let msg = `Pedido:%0A- Batata%0AQuantidade: ${qtd}%0AAdicionais: ${adicionais}`;
  abrirWhats(msg);
}

// WhatsApp
function abrirWhats(msg) {
  let numero = "55859929265249";
  let url = `https://wa.me/${numero}?text=${msg}`;
  window.open(url, '_blank');
}

</script>

</body>
</html>
