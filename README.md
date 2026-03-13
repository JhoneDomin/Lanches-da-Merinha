# Lanches-da-Merinha
Lanchonete
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Lanches da Merinha</title>

<style>

body{
font-family:Arial;
background:#fff5e6;
margin:0;
}

header{
background:#ff7a00;
color:white;
text-align:center;
padding:20px;
font-size:28px;
}

.container{
padding:20px;
max-width:600px;
margin:auto;
}

h2{
color:#ff7a00;
margin-top:30px;
}

.produto{
background:white;
padding:15px;
border-radius:10px;
margin-bottom:10px;
box-shadow:0 3px 10px rgba(0,0,0,0.1);
}

.preco{
color:#ff3c00;
font-weight:bold;
}

input{
width:60px;
padding:5px;
}

button{
background:#25D366;
color:white;
border:none;
padding:15px;
font-size:18px;
border-radius:8px;
width:100%;
margin-top:20px;
cursor:pointer;
}

</style>

</head>

<body>

<header>
Lanches da Merinha
</header>

<div class="container">

<h2>Pastéis de 14 cm</h2>

<div class="produto">Carne - <span class="preco">R$6</span>
<br>Quantidade: <input type="number" id="carne14" value="0" min="0"></div>

<div class="produto">Misto - <span class="preco">R$6</span>
<br>Quantidade: <input type="number" id="misto14" value="0" min="0"></div>

<div class="produto">Mistão - <span class="preco">R$6</span>
<br>Quantidade: <input type="number" id="mistao14" value="0" min="0"></div>

<div class="produto">Carne com Queijo - <span class="preco">R$6</span>
<br>Quantidade: <input type="number" id="carneq14" value="0" min="0"></div>

<div class="produto">Frango com Queijo - <span class="preco">R$6</span>
<br>Quantidade: <input type="number" id="frangoq14" value="0" min="0"></div>

<div class="produto">Frango - <span class="preco">R$6</span>
<br>Quantidade: <input type="number" id="frango14" value="0" min="0"></div>

<div class="produto">Queijo - <span class="preco">R$6</span>
<br>Quantidade: <input type="number" id="queijo14" value="0" min="0"></div>

<div class="produto">Pizza - <span class="preco">R$6</span>
<br>Quantidade: <input type="number" id="pizza14" value="0" min="0"></div>

<h2>Pastéis de 24 cm</h2>

<div class="produto">Carne - <span class="preco">R$8</span>
<br>Quantidade: <input type="number" id="carne24" value="0" min="0"></div>

<div class="produto">Misto - <span class="preco">R$8</span>
<br>Quantidade: <input type="number" id="misto24" value="0" min="0"></div>

<div class="produto">Mistão - <span class="preco">R$8</span>
<br>Quantidade: <input type="number" id="mistao24" value="0" min="0"></div>

<div class="produto">Carne com Queijo - <span class="preco">R$8</span>
<br>Quantidade: <input type="number" id="carneq24" value="0" min="0"></div>

<div class="produto">Frango com Queijo - <span class="preco">R$8</span>
<br>Quantidade: <input type="number" id="frangoq24" value="0" min="0"></div>

<div class="produto">Frango - <span class="preco">R$8</span>
<br>Quantidade: <input type="number" id="frango24" value="0" min="0"></div>

<div class="produto">Queijo - <span class="preco">R$8</span>
<br>Quantidade: <input type="number" id="queijo24" value="0" min="0"></div>

<div class="produto">Pizza - <span class="preco">R$8</span>
<br>Quantidade: <input type="number" id="pizza24" value="0" min="0"></div>

<h2>Adicionais</h2>

<div class="produto">Catupiry - R$1
<br>Quantidade: <input type="number" id="catupiry" value="0" min="0"></div>

<div class="produto">Maionese - R$1
<br>Quantidade: <input type="number" id="maionese" value="0" min="0"></div>

<div class="produto">Cheddar - R$1
<br>Quantidade: <input type="number" id="cheddar" value="0" min="0"></div>

<div class="produto">Ketchup - R$1
<br>Quantidade: <input type="number" id="ketchup" value="0" min="0"></div>

<div class="produto">Milho - R$1
<br>Quantidade: <input type="number" id="milho" value="0" min="0"></div>

<div class="produto">Azeitona - R$1
<br>Quantidade: <input type="number" id="azeitona" value="0" min="0"></div>

<div class="produto">Verdura - R$1
<br>Quantidade: <input type="number" id="verdura" value="0" min="0"></div>

<button onclick="enviarPedido()">Enviar pedido no WhatsApp</button>

</div>

<script>

function enviarPedido(){

let total = 0
let mensagem = "Pedido:%0A"

function add(nome,id,preco){

let q = document.getElementById(id).value

if(q>0){
mensagem += q + " " + nome + "%0A"
total += q * preco
}

}

add("Pastel 14cm Carne","carne14",6)
add("Pastel 14cm Misto","misto14",6)
add("Pastel 14cm Mistão","mistao14",6)
add("Pastel 14cm Carne com Queijo","carneq14",6)
add("Pastel 14cm Frango com Queijo","frangoq14",6)
add("Pastel 14cm Frango","frango14",6)
add("Pastel 14cm Queijo","queijo14",6)
add("Pastel 14cm Pizza","pizza14",6)

add("Pastel 24cm Carne","carne24",8)
add("Pastel 24cm Misto","misto24",8)
add("Pastel 24cm Mistão","mistao24",8)
add("Pastel 24cm Carne com Queijo","carneq24",8)
add("Pastel 24cm Frango com Queijo","frangoq24",8)
add("Pastel 24cm Frango","frango24",8)
add("Pastel 24cm Queijo","queijo24",8)
add("Pastel 24cm Pizza","pizza24",8)

add("Catupiry","catupiry",1)
add("Maionese","maionese",1)
add("Cheddar","cheddar",1)
add("Ketchup","ketchup",1)
add("Milho","milho",1)
add("Azeitona","azeitona",1)
add("Verdura","verdura",1)

mensagem += "%0ATotal: R$" + total

let numero = "5585991923386"

let url = "https://wa.me/" + numero + "?text=" + mensagem

window.open(url)

}

</script>

</body>
</html>
