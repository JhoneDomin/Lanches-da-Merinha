<html lang="pt-br">
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

.box{
background:white;
padding:15px;
border-radius:12px;
margin-bottom:12px;
box-shadow:0 4px 10px rgba(0,0,0,0.1);
}

label{display:block;margin:5px 0;}
select,input{padding:5px;margin-top:5px;}

button{
background:#25D366;
color:white;
border:none;
padding:15px;
border-radius:10px;
width:100%;
margin-top:10px;
font-size:16px;
}

.btnAdd{background:#ff7a00;}
.btnRemove{background:#ff3c00;}

.totalBox{
background:#fff;
border:2px solid #ff7a00;
padding:15px;
border-radius:12px;
text-align:center;
font-size:20px;
margin-top:20px;
}
</style>
</head>

<body>

<header>🍔 Lanches da Merinha</header>

<div class="container">

<h1>🥟 Pastéis</h1>
<div id="pasteis"></div>
<button class="btnAdd" onclick="addPastel()">➕ Adicionar pastel</button>

<h1>🍛 Pratinhos</h1>
<div id="pratinhos"></div>
<button class="btnAdd" onclick="addPratinho()">➕ Adicionar pratinho</button>

<h1>🍟 Batatinhas</h1>
<div id="batatas"></div>
<button class="btnAdd" onclick="addBatata()">➕ Adicionar batata</button>

<div class="totalBox">
Total: R$ <span id="total">0</span>
</div>

<button onclick="enviarPedido()">Enviar pedido no WhatsApp</button>

</div>

<!-- 🧾 RESUMO -->
<div id="resumoBox" style="display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:#000000cc; justify-content:center; align-items:center;">
<div style="background:white; padding:20px; border-radius:12px; width:90%; max-width:400px; max-height:80%; overflow:auto;">
<h2>🧾 Resumo do Pedido</h2>
<div id="resumoConteudo"></div>
<button onclick="confirmarPedido()">✅ Confirmar Pedido</button>
<button onclick="fecharResumo()" class="btnRemove">❌ Cancelar</button>
</div>
</div>

<script>
let countPastel=0, countPrato=0, countBatata=0;

// ===== PASTEL =====
function addPastel(){
countPastel++;

let div=document.createElement("div");
div.className="box";

div.innerHTML=`
<h3>Pastel ${countPastel}</h3>

<label>Tamanho:</label>
<select class="tam">
<option value="6">14 cm - R$6</option>
<option value="8">24 cm - R$8</option>
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

<button class="btnRemove" onclick="this.parentElement.remove(); atualizarTotal()">❌ Remover</button>
`;

document.getElementById("pasteis").appendChild(div);
atualizarTotal();
}

// ===== PRATINHO =====
function addPratinho(){
countPrato++;

let div=document.createElement("div");
div.className="box";

div.innerHTML=`
<h3>Pratinho ${countPrato}</h3>

<label>Tipo:</label>
<select class="tipo">
<option value="8">Tradicional - R$8</option>
<option value="11">Estou com Fome - R$11</option>
</select>

<p>Adicionais:</p>
<label><input type="checkbox" value="Arroz"> Arroz</label>
<label><input type="checkbox" value="Farofa"> Farofa</label>
<label><input type="checkbox" value="Salada"> Salada</label>
<label><input type="checkbox" value="Vinagrete"> Vinagrete</label>
<label><input type="checkbox" value="Vatapá"> Vatapá</label>

<button class="btnRemove" onclick="this.parentElement.remove(); atualizarTotal()">❌ Remover</button>
`;

document.getElementById("pratinhos").appendChild(div);
atualizarTotal();
}

// ===== BATATA =====
function addBatata(){
countBatata++;

let div=document.createElement("div");
div.className="box";

div.innerHTML=`
<h3>Batata ${countBatata}</h3>

<label>Tipo:</label>
<select class="tipo">
<option value="11">Simples - R$11</option>
<option value="13">Com Calabresa - R$13</option>
<option value="11">Macaxeira - R$11</option>
</select>

<p>Adicionais:</p>
<label><input type="checkbox" value="Ketchup"> Ketchup</label>
<label><input type="checkbox" value="Maionese"> Maionese</label>
<label><input type="checkbox" value="Cheddar"> Cheddar</label>
<label><input type="checkbox" value="Catupiry"> Catupiry</label>

<button class="btnRemove" onclick="this.parentElement.remove(); atualizarTotal()">❌ Remover</button>
`;

document.getElementById("batatas").appendChild(div);
atualizarTotal();
}

// ===== TOTAL =====
function atualizarTotal(){
let total=0;

document.querySelectorAll("#pasteis .tam").forEach(s=> total+=parseInt(s.value));
document.querySelectorAll("#pratinhos .tipo").forEach(s=> total+=parseInt(s.value));
document.querySelectorAll("#batatas .tipo").forEach(s=> total+=parseInt(s.value));

document.getElementById("total").innerText=total;
}

document.addEventListener("change", atualizarTotal);

// inicial
addPastel();

// ===== RESUMO =====
function enviarPedido(){
let html="";
let total=document.getElementById("total").innerText;

// PASTEIS
document.querySelectorAll("#pasteis .box").forEach((p,i)=>{
let sabor=p.querySelector(".sabor").value;
let tamanho=p.querySelector(".tam").selectedOptions[0].text;

let add=[];
p.querySelectorAll("input:checked").forEach(c=>add.push(c.value));

html+=`<b>Pastel ${i+1}:</b> ${sabor} (${tamanho})`;
if(add.length) html+="<br>➕ "+add.join(", ");
html+="<br><br>";
});

// PRATINHOS
document.querySelectorAll("#pratinhos .box").forEach((p,i)=>{
let tipo=p.querySelector(".tipo").selectedOptions[0].text;

let add=[];
p.querySelectorAll("input:checked").forEach(c=>add.push(c.value));

html+=`<b>Pratinho ${i+1}:</b> ${tipo}`;
if(add.length) html+="<br>➕ "+add.join(", ");
html+="<br><br>";
});

// BATATAS
document.querySelectorAll("#batatas .box").forEach((p,i)=>{
let tipo=p.querySelector(".tipo").selectedOptions[0].text;

let add=[];
p.querySelectorAll("input:checked").forEach(c=>add.push(c.value));

html+=`<b>Batata ${i+1}:</b> ${tipo}`;
if(add.length) html+="<br>➕ "+add.join(", ");
html+="<br><br>";
});

html+=`<hr><b>Total: R$ ${total}</b>`;

document.getElementById("resumoConteudo").innerHTML=html;
document.getElementById("resumoBox").style.display="flex";
}

function fecharResumo(){
document.getElementById("resumoBox").style.display="none";
}

// ===== WHATSAPP =====
function confirmarPedido(){
let msg="Pedido:%0A";

document.querySelectorAll(".box").forEach((p,i)=>{
let titulo=p.querySelector("h3").innerText;

let tipo = p.querySelector("select")?.selectedOptions[0].text || "";

let add=[];
p.querySelectorAll("input:checked").forEach(c=>add.push(c.value));

msg+=`%0A${titulo}: ${tipo}`;
if(add.length) msg+=" - "+add.join(", ");
msg+="%0A";
});

msg+=`%0ATotal: R$ ${document.getElementById("total").innerText}`;

window.open("https://wa.me/5585992265249?text="+msg);
}
</script>

</body>
</html>
