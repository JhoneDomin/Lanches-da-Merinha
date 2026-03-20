xh<head>
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
<div class="container"><h1>🥟 Pastéis</h1>
<h2>14 cm</h2>
<div class="produto">Carne - <span class="preco">R$6</span><br><input type="number" id="carne14" value="0" min="0"></div>
<div class="produto">Misto - <span class="preco">R$6</span><br><input type="number" id="misto14" value="0" min="0"></div>
<div class="produto">Mistão - <span class="preco">R$6</span><br><input type="number" id="mistao14" value="0" min="0"></div>
<div class="produto">Carne c/ Queijo - <span class="preco">R$6</span><br><input type="number" id="carneq14" value="0" min="0"></div>
<div class="produto">Frango c/ Queijo - <span class="preco">R$6</span><br><input type="number" id="frangoq14" value="0" min="0"></div>
<div class="produto">Frango - <span class="preco">R$6</span><br><input type="number" id="frango14" value="0" min="0"></div>
<div class="produto">Queijo - <span class="preco">R$6</span><br><input type="number" id="queijo14" value="0" min="0"></div>
<div class="produto">Pizza - <span class="preco">R$6</span><br><input type="number" id="pizza14" value="0" min="0"></div><h2>24 cm</h2>
<div class="produto">Carne - <span class="preco">R$8</span><br><input type="number" id="carne24" value="0" min="0"></div>
<div class="produto">Misto - <span class="preco">R$8</span><br><input type="number" id="misto24" value="0" min="0"></div>
<div class="produto">Mistão - <span class="preco">R$8</span><br><input type="number" id="mistao24" value="0" min="0"></div>
<div class="produto">Carne c/ Queijo - <span class="preco">R$8</span><br><input type="number" id="carneq24" value="0" min="0"></div>
<div class="produto">Frango c/ Queijo - <span class="preco">R$8</span><br><input type="number" id="frangoq24" value="0" min="0"></div>
<div class="produto">Frango - <span class="preco">R$8</span><br><input type="number" id="frango24" value="0" min="0"></div>
<div class="produto">Queijo - <span class="preco">R$8</span><br><input type="number" id="queijo24" value="0" min="0"></div>
<div class="produto">Pizza - <span class="preco">R$8</span><br><input type="number" id="pizza24" value="0" min="0"></div><h2>Adicionais (Grátis)</h2>
<div class="produto">Catupiry <input type="number" id="catupiry" value="0" min="0"></div>
<div class="produto">Maionese <input type="number" id="maionese" value="0" min="0"></div>
<div class="produto">Cheddar <input type="number" id="cheddar" value="0" min="0"></div>
<div class="produto">Ketchup <input type="number" id="ketchup" value="0" min="0"></div>
<div class="produto">Milho <input type="number" id="milho" value="0" min="0"></div>
<div class="produto">Azeitona <input type="number" id="azeitona" value="0" min="0"></div>
<div class="produto">Verduras <input type="number" id="verdura" value="0" min="0"></div><h1>🍛 Pratinhos</h1>
<div class="card" id="card1">
<h3>Tradicional - R$8</h3>
Quantidade: <input type="number" id="pratinho1" value="0" min="0">
<label><input type="checkbox"> Arroz</label>
<label><input type="checkbox"> Farofa</label>
<label><input type="checkbox"> Salada</label>
<label><input type="checkbox"> Vinagrete</label>
<label><input type="checkbox"> Creme de Galinha</label>
<label><input type="checkbox"> Escondidinho</label>
<label><input type="checkbox"> Vatapá</label>
</div><div class="card" id="card2">
<h3>Estou com Fome - R$11</h3>
Quantidade: <input type="number" id="pratinho2" value="0" min="0">
<label><input type="checkbox"> Baião</label>
<label><input type="checkbox"> Vatapá</label>
<label><input type="checkbox"> Escondidinho</label>
<label><input type="checkbox"> Paçoca</label>
<label><input type="checkbox"> Macaxeira</label>
</div><h2>Adicionais (R$3)</h2>
<div class="card">
<label><input type="checkbox" id="batataExtra"> Batata frita</label>
<label><input type="checkbox" id="calabresaExtra"> Calabresa</label>
</div><h1>🍟 Batatinhas</h1><div class="card">
<h3>Batata Simples - R$11</h3>
Quantidade: <input type="number" id="batataSimples" value="0" min="0">
<label><input type="checkbox"> Ketchup</label>
<label><input type="checkbox"> Maionese</label>
<label><input type="checkbox"> Cheddar</label>
<label><input type="checkbox"> Catupiry</label>
</div><div class="card">
<h3>Batata com Calabresa - R$13</h3>
Quantidade: <input type="number" id="batataCalabresa" value="0" min="0">
<label><input type="checkbox"> Ketchup</label>
<label><input type="checkbox"> Maionese</label>
<label><input type="checkbox"> Cheddar</label>
<label><input type="checkbox"> Catupiry</label>
</div><div class="card">
<h3>Macaxeira - R$11</h3>
Quantidade: <input type="number" id="macaxeira" value="0" min="0">
<label><input type="checkbox"> Ketchup</label>
<label><input type="checkbox"> Maionese</label>
<label><input type="checkbox"> Cheddar</label>
<label><input type="checkbox"> Catupiry</label>
</div><button onclick="enviarPedido()">Enviar pedido no WhatsApp</button>

</div><script>
function enviarPedido(){
let total=0
let mensagem="Pedido:%0A"

function add(nome,id,preco){
let q=document.getElementById(id)?.value
if(q>0){mensagem+=q+" "+nome+"%0A"; total+=q*preco}}

// Pastéis
add("Pastel 14 Carne","carne14",6)
add("Pastel 14 Misto","misto14",6)
add("Pastel 14 Mistão","mistao14",6)
add("Pastel 14 Carne c/ queijo","carneq14",6)
add("Pastel 14 Frango c/ queijo","frangoq14",6)
add("Pastel 14 Frango","frango14",6)
add("Pastel 14 Queijo","queijo14",6)
add("Pastel 14 Pizza","pizza14",6)
add("Pastel 24 Carne","carne24",8)
add("Pastel 24 Misto","misto24",8)
add("Pastel 24 Mistão","mistao24",8)
add("Pastel 24 Carne c/ queijo","carneq24",8)
add("Pastel 24 Frango c/ queijo","frangoq24",8)
add("Pastel 24 Frango","frango24",8)
add("Pastel 24 Queijo","queijo24",8)
add("Pastel 24 Pizza","pizza24",8)

if(document.getElementById('batataExtra')?.checked){total+=3; mensagem+="+ Batata Extra%0A"}
if(document.getElementById('calabresaExtra')?.checked){total+=3; mensagem+="+ Calabresa Extra%0A"}

// PRATINHOS
function addPratinho(nome, preco, id, container){
let q=document.getElementById(id)?.value
if(q>0){
let itens=[]
container.querySelectorAll("input[type='checkbox']:checked").forEach(c=>{
 itens.push(c.parentElement.innerText.trim())
})
mensagem+=q+" "+nome
if(itens.length>0){mensagem+=" ("+itens.join(', ')+")"}
mensagem+="%0A"
total+=q*preco
}
}

addPratinho("Pratinho Tradicional",8,"pratinho1",document.getElementById('card1'))
addPratinho("Pratinho Estou com Fome",11,"pratinho2",document.getElementById('card2'))

// BATATINHAS
function addBatata(nome,id,preco){
let q=document.getElementById(id)?.value
if(q>0){
let adicionais=[]
let checks=document.querySelectorAll(`#${id} ~ label input:checked`)
checks.forEach(c=>adicionais.push(c.parentElement.innerText.trim()))
mensagem+=q+" "+nome
if(adicionais.length>0){mensagem+=" ("+adicionais.join(', ')+")"}
mensagem+="%0A"
total+=q*preco
}}

addBatata("Batata Simples","batataSimples",11)
addBatata("Batata com Calabresa","batataCalabresa",13)
addBatata("Macaxeira","macaxeira",11)

mensagem+="%0ATotal: R$"+total
let numero="55(85)992265249"
window.open("https://wa.me/"+numero+"?text="+mensagem)
}
</script></body>
</html>
