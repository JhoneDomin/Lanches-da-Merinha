<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lanches da Merinha</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Poppins',sans-serif;}
body{background:#fff5e6;}
header{background:linear-gradient(90deg,#ff7a00,#ff9a3c);color:white;text-align:center;padding:20px;font-size:26px;}
.container{padding:20px;max-width:800px;margin:auto;}
h1{margin-top:25px;color:#333;}
h2{color:#ff7a00;margin:15px 0;}
.produto{background:white;padding:15px;border-radius:12px;margin-bottom:12px;box-shadow:0 4px 10px rgba(0,0,0,0.1);} 
.preco{color:#ff3c00;font-weight:bold;}
input{width:60px;padding:5px;margin-top:5px;}
label{display:block;margin:5px 0;}
button{background:#25D366;color:white;border:none;padding:15px;font-size:16px;border-radius:10px;width:100%;margin-top:20px;cursor:pointer;}
.card{background:white;padding:15px;border-radius:12px;margin-bottom:12px;box-shadow:0 4px 10px rgba(0,0,0,0.1);} 
</style>
</head>

<body>

<header>🍔 Lanches da Merinha</header>

<div class="container">

<h1>🥟 Pastéis</h1>

<h2>14 cm</h2>

<div class="produto">Carne - <span class="preco">R$6</span><br><input type="number" id="carne14" value="0" min="0"></div>
<div class="produto">Misto - <span class="preco">R$6</span><br><input type="number" id="misto14" value="0" min="0"></div>

<h2>24 cm</h2>

<div class="produto">Carne - <span class="preco">R$8</span><br><input type="number" id="carne24" value="0" min="0"></div>
<div class="produto">Misto - <span class="preco">R$8</span><br><input type="number" id="misto24" value="0" min="0"></div>

<h2>Adicionais (Grátis)</h2>
<div class="produto" id="adicionaisPastel">
<label><input type="checkbox" value="Catupiry"> Catupiry</label>
<label><input type="checkbox" value="Maionese"> Maionese</label>
<label><input type="checkbox" value="Cheddar"> Cheddar</label>
<label><input type="checkbox" value="Ketchup"> Ketchup</label>
<label><input type="checkbox" value="Milho"> Milho</label>
<label><input type="checkbox" value="Azeitona"> Azeitona</label>
<label><input type="checkbox" value="Verduras"> Verduras</label>
</div>

<button onclick="enviarPedido()">Enviar pedido no WhatsApp</button>

</div>

<script>
function enviarPedido(){
let total=0
let mensagem="Pedido:%0A"

function getAdicionais(){
let lista=[]
document.querySelectorAll("#adicionaisPastel input:checked").forEach(c=>{
lista.push(c.value)
})
return lista.length>0 ? " ("+lista.join(', ')+")" : ""
}

function add(nome,id,preco){
let q=document.getElementById(id)?.value
if(q>0){
let adicionais=getAdicionais()
mensagem+=q+" "+nome+adicionais+"%0A"
total+=q*preco
}}

// Pastéis 14 cm
add("Pastel 14 cm Carne","carne14",6)
add("Pastel 14 cm Misto","misto14",6)

// Pastéis 24 cm
add("Pastel 24 cm Carne","carne24",8)
add("Pastel 24 cm Misto","misto24",8)

mensagem+="%0ATotal: R$"+total

let numero="5585992265249"
window.open("https://wa.me/"+numero+"?text="+mensagem)
}
</script>

</body>
</html>
