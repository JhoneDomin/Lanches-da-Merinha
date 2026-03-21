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
.produto, .pastelBox{background:white;padding:15px;border-radius:12px;margin-bottom:12px;box-shadow:0 4px 10px rgba(0,0,0,0.1);}
.preco{color:#ff3c00;font-weight:bold;}
input, select{padding:5px;margin-top:5px;}
label{display:block;margin:5px 0;}
button{background:#25D366;color:white;border:none;padding:15px;font-size:16px;border-radius:10px;width:100%;margin-top:20px;cursor:pointer;}
.btnAdd{background:#ff7a00;margin-top:10px;}
.btnRemove{background:#ff3c00;margin-top:10px;}
</style>
</head>
<body>

<header>🍔 Lanches da Merinha</header>

<div class="container">

<h1>🥟 Pastéis</h1>

<div id="listaPasteis"></div>

<button class="btnAdd" onclick="adicionarPastel()">➕ Adicionar outro pastel</button>

<h1>🍛 Pratinhos</h1>

<div class="card" id="card1">
<h3>Tradicional - R$8</h3>
Quantidade: <input type="number" id="pratinho1" value="0" min="0">
<label><input type="checkbox"> Arroz</label>
<label><input type="checkbox"> Farofa</label>
<label><input type="checkbox"> Salada</label>
<label><input type="checkbox"> Vinagrete</label>
<label><input type="checkbox"> Creme de Galinha</label>
<label><input type="checkbox"> Escondidinho de Carne</label>
<label><input type="checkbox"> Vatapá</label>
</div>

<div class="card" id="card2">
<h3>Estou com Fome - R$11</h3>
Quantidade: <input type="number" id="pratinho2" value="0" min="0">
<label><input type="checkbox"> Baião</label>
<label><input type="checkbox"> Vatapá</label>
<label><input type="checkbox"> Escondidinho de Carne</label>
<label><input type="checkbox"> Paçoca</label>
<label><input type="checkbox"> Macaxeira</label>
</div>

<h2>Adicionais (R$3)</h2>
<div class="card">
<label><input type="checkbox" id="batataExtra"> Batata frita</label>
<label><input type="checkbox" id="calabresaExtra"> Calabresa</label>
</div>

<h1>🍟 Batatinhas</h1>

<div class="card">
<h3>Batata Simples - R$11</h3>
Quantidade: <input type="number" id="batataSimples" value="0" min="0">
<label><input type="checkbox"> Ketchup</label>
<label><input type="checkbox"> Maionese</label>
<label><input type="checkbox"> Cheddar</label>
<label><input type="checkbox"> Catupiry</label>
</div>

<div class="card">
<h3>Batata com Calabresa - R$13</h3>
Quantidade: <input type="number" id="batataCalabresa" value="0" min="0">
<label><input type="checkbox"> Ketchup</label>
<label><input type="checkbox"> Maionese</label>
<label><input type="checkbox"> Cheddar</label>
<label><input type="checkbox"> Catupiry</label>
</div>

<div class="card">
<h3>Macaxeira - R$11</h3>
Quantidade: <input type="number" id="macaxeira" value="0" min="0">
<label><input type="checkbox"> Ketchup</label>
<label><input type="checkbox"> Maionese</label>
<label><input type="checkbox"> Cheddar</label>
<label><input type="checkbox"> Catupiry</label>
</div>

<button onclick="enviarPedido()">Enviar pedido no WhatsApp</button>

</div>

<script>
let contador = 0;

function adicionarPastel(){
contador++;

let div = document.createElement("div");
div.className = "pastelBox";

div.innerHTML = `
<h3>Pastel ${contador}</h3>

<label>Tamanho:</label>
<select class="tamanho">
<option value="14">14 cm</option>
<option value="24">24 cm</option>
</select>

<label>Sabor:</label>
<select class="sabor">
<option>Carne</option>
<option>Misto</option>
<option>Mistão</option>
<option>Carne c/ queijo</option>
<option>Frango c/ queijo</option>
<option>Frango</option>
<option>Queijo</option>
<option>Pizza</option>
</select>

<p>Adicionais:</p>
<label><input type="checkbox" value="Catupiry"> Catupiry</label>
<label><input type="checkbox" value="Maionese"> Maionese</label>
<label><input type="checkbox" value="Cheddar"> Cheddar</label>
<label><input type="checkbox" value="Ketchup"> Ketchup</label>
<label><input type="checkbox" value="Milho"> Milho</label>
<label><input type="checkbox" value="Azeitona"> Azeitona</label>
<label><input type="checkbox" value="Verduras"> Verduras</label>

<button class="btnRemove" onclick="removerPastel(this)">❌ Remover pastel</button>
`;

document.getElementById("listaPasteis").appendChild(div);
}

// remover
function removerPastel(botao){
botao.parentElement.remove();
reorganizar();
}

// reorganiza numeração
function reorganizar(){
let todos = document.querySelectorAll(".pastelBox h3");
todos.forEach((el, i)=>{
el.innerText = "Pastel " + (i+1);
});
contador = todos.length;
}

// inicial
adicionarPastel();

function enviarPedido(){
let total = 0;
let mensagem = "Pedido:%0A";

// PASTEIS
document.querySelectorAll(".pastelBox").forEach((p, i)=>{
let tamanho = p.querySelector(".tamanho").value;
let sabor = p.querySelector(".sabor").value;

let adicionais = [];
p.querySelectorAll("input:checked").forEach(c=>{
adicionais.push(c.value);
});

mensagem += `%0APastel ${i+1}: ${sabor} (${tamanho} cm)`;

if(adicionais.length>0){
mensagem += " - " + adicionais.join(", ");
}

mensagem += "%0A";

total += (tamanho == 14 ? 6 : 8);
});

// extras
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

mensagem+="%0ATotal: R$"+total

let numero="5585992265249"
window.open("https://wa.me/"+numero+"?text="+mensagem)
}
</script>

</body>
</html>
