<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<title>Lanches Meirinha</title>

<style>
body {
  font-family: Arial;
  padding: 20px;
  background: #f5f5f5;
}

h1 {
  text-align: center;
}

h2 {
  margin-top: 30px;
}

.item {
  background: #fff;
  border: 1px solid #ccc;
  padding: 15px;
  margin-bottom: 15px;
  border-radius: 8px;
}

button {
  padding: 10px;
  margin-top: 10px;
  width: 100%;
  background: green;
  color: #fff;
  border: none;
  border-radius: 5px;
  font-weight: bold;
}

input[type="number"] {
  width: 60px;
}
</style>
</head>

<body>

<h1>Lanches Meirinha</h1>

<!-- ================= PASTÉIS ================= -->
<h2>Pastéis</h2>

<div class="item">
  <strong>Pastel 24 cm - R$ 10,00</strong><br><br>

  <strong>Adicionais:</strong><br>
  <input type="checkbox" value="Queijo"> Queijo<br>
  <input type="checkbox" value="Presunto"> Presunto<br>

  <br><strong>Quantidade:</strong>
  <input type="number" min="1" value="1" id="qtdPastel">

  <br><button onclick="enviarPastel(event)">Pedir pelo WhatsApp</button>
</div>

<!-- ================= PRATINHOS ================= -->
<h2>Pratinhos</h2>

<div class="item">
  <strong>Pratinho - R$ 12,00</strong><br><br>

  <strong>Adicionais:</strong><br>
  <input type="checkbox" value="Queijo"> Queijo<br>
  <input type="checkbox" value="Presunto"> Presunto<br>
  <input type="checkbox" value="Ovo"> Ovo<br>

  <br><strong>Quantidade:</strong>
  <input type="number" min="1" value="1" id="qtdPratinho">

  <br><button onclick="enviarPratinho(event)">Pedir pelo WhatsApp</button>
</div>

<!-- ================= BATATINHAS ================= -->
<h2>Batatinhas</h2>

<div class="item">
  <strong>Batata - R$ 8,00</strong><br><br>

  <strong>Adicionais:</strong><br>
  <input type="checkbox" value="Queijo"> Queijo<br>
  <input type="checkbox" value="Bacon"> Bacon<br>
  <input type="checkbox" value="Catupiry"> Catupiry<br>

  <br><strong>Quantidade:</strong>
  <input type="number" min="1" value="1" id="qtdBatata">

  <br><button onclick="enviarBatata(event)">Pedir pelo WhatsApp</button>
</div>

<script>

// Função para pegar adicionais do item clicado
function pegarAdicionais(botao) {
  let adicionais = [];
  let container = botao.parentElement;
  let checks = container.querySelectorAll('input[type="checkbox"]:checked');

  checks.forEach(c => adicionais.push(c.value));

  return adicionais.length > 0 ? adicionais.join(", ") : "Nenhum";
}

// ===== Pastel =====
function enviarPastel(e) {
  let qtd = document.getElementById("qtdPastel").value;
  let adicionais = pegarAdicionais(e.target);

  let msg = `Pedido:%0A- Pastel 24 centímetros%0AQuantidade: ${qtd}%0AAdicionais: ${adicionais}`;
  abrirWhats(msg);
}

// ===== Pratinho =====
function enviarPratinho(e) {
  let qtd = document.getElementById("qtdPratinho").value;
  let adicionais = pegarAdicionais(e.target);

  let msg = `Pedido:%0A- Pratinho%0AQuantidade: ${qtd}%0AAdicionais: ${adicionais}`;
  abrirWhats(msg);
}

// ===== Batata =====
function enviarBatata(e) {
  let qtd = document.getElementById("qtdBatata").value;
  let adicionais = pegarAdicionais(e.target);

  let msg = `Pedido:%0A- Batata%0AQuantidade: ${qtd}%0AAdicionais: ${adicionais}`;
  abrirWhats(msg);
}

// ===== WhatsApp =====
function abrirWhats(msg) {
  let numero = "55859929265249";
  let url = `https://wa.me/${numero}?text=${msg}`;
  window.open(url, '_blank');
}

</script>

</body>
</html>>
