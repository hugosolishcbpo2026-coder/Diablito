<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body{margin:0;font-family:Arial;background:#050505;color:#fff;text-align:center}
.header{background:#000;padding:15px;border-bottom:1px solid #222}
.logo{font-size:1.8rem;color:#ff1a1a}
.hero{padding:30px}
.hero h1{text-shadow:0 0 15px red}
.trust{font-size:0.9rem;opacity:0.8;margin-bottom:10px}
.video{padding:10px}
.video video{width:90%;border-radius:10px}

.promo{background:#ff1a1a;padding:10px;font-weight:bold;}

.products{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(140px,1fr));
gap:12px;
padding:15px
}

.card{
background:#111;
border-radius:10px;
overflow:hidden;
box-shadow:0 0 10px rgba(255,0,0,0.3);
padding-bottom:10px;
}

.card img{width:100%;height:140px;object-fit:cover}

select,input{
width:90%;
margin:5px 0;
padding:6px;
}

input{display:none;}

button{
background:#25D366;
color:#fff;
border:none;
padding:10px;
width:90%;
font-weight:bold;
cursor:pointer;
}
</style>
</head>

<body>

<div class="header"><div class="logo">🔥 DIABLITO</div></div>

<div class="hero">
<h1>Premium Smoke Experience</h1>
<p>Order instantly via WhatsApp</p>
<div class="trust">🚚 Same Day Delivery • 🔒 Discreet • ⭐ Trusted in Tijuana</div>
</div>

<div class="promo">🔥 BUY MORE = BETTER DEALS 🔥</div>

<div class="video">
<video controls>
<source src="GrowHub.mp4" type="video/mp4">
</video>
</div>

<div class="products">

<div class="card">
<img src="strain1.jpg">
<h3>Premium Strain 🔥</h3>

<select id="size1">
<option value="0.125">1/8 oz</option>
<option value="0.5">1/2 oz</option>
<option value="1">1 oz</option>
<option value="16">1 lb</option>
</select>

<select id="qty1" onchange="toggleCustomQty('qty1','custom1')">
<option value="1">Qty: 1</option>
<option value="2">Qty: 2</option>
<option value="3">Qty: 3</option>
<option value="4">Qty: 4</option>
<option value="5">Qty: 5</option>
<option value="custom">More...</option>
</select>

<input type="number" id="custom1" placeholder="Enter quantity">

<button onclick="order('Premium Strain','size1','qty1','custom1')">
Order on WhatsApp
</button>
</div>

<div class="card">
<img src="strain2.jpg">
<h3>Exotic Strain 💨</h3>

<select id="size2">
<option value="0.125">1/8 oz</option>
<option value="0.5">1/2 oz</option>
<option value="1">1 oz</option>
<option value="16">1 lb</option>
</select>

<select id="qty2" onchange="toggleCustomQty('qty2','custom2')">
<option value="1">Qty: 1</option>
<option value="2">Qty: 2</option>
<option value="3">Qty: 3</option>
<option value="4">Qty: 4</option>
<option value="5">Qty: 5</option>
<option value="custom">More...</option>
</select>

<input type="number" id="custom2" placeholder="Enter quantity">

<button onclick="order('Exotic Strain','size2','qty2','custom2')">
Order on WhatsApp
</button>
</div>

<div class="card">
<img src="strain3.jpg">
<h3>Top Shelf Strain 🌿</h3>

<select id="size3">
<option value="0.125">1/8 oz</option>
<option value="0.5">1/2 oz</option>
<option value="1">1 oz</option>
<option value="16">1 lb</option>
</select>

<select id="qty3" onchange="toggleCustomQty('qty3','custom3')">
<option value="1">Qty: 1</option>
<option value="2">Qty: 2</option>
<option value="3">Qty: 3</option>
<option value="4">Qty: 4</option>
<option value="5">Qty: 5</option>
<option value="custom">More...</option>
</select>

<input type="number" id="custom3" placeholder="Enter quantity">

<button onclick="order('Top Shelf Strain','size3','qty3','custom3')">
Order on WhatsApp
</button>
</div>

<div class="card">
<img src="allstrains.jpg">
<h3>All Strains Pack</h3>

<select id="size4">
<option value="0.125">1/8 oz</option>
<option value="0.5">1/2 oz</option>
<option value="1">1 oz</option>
<option value="16">1 lb</option>
</select>

<select id="qty4" onchange="toggleCustomQty('qty4','custom4')">
<option value="1">Qty: 1</option>
<option value="2">Qty: 2</option>
<option value="3">Qty: 3</option>
<option value="4">Qty: 4</option>
<option value="5">Qty: 5</option>
<option value="custom">More...</option>
</select>

<input type="number" id="custom4" placeholder="Enter quantity">

<button onclick="order('All Strains Pack','size4','qty4','custom4')">
Order on WhatsApp
</button>
</div>

</div>

<script>
const pricePerOz = 376.47;

function toggleCustomQty(selectId, inputId){
const select = document.getElementById(selectId);
const input = document.getElementById(inputId);
input.style.display = (select.value === "custom") ? "block" : "none";
}

function getDiscount(qty){
if(qty >= 10) return 0.20;
if(qty >= 5) return 0.10;
return 0;
}

function sizeLabel(size){
if(size == 0.125) return "1/8 oz";
if(size == 0.5) return "1/2 oz";
if(size == 1) return "1 oz";
if(size == 16) return "1 lb";
return size + " oz";
}

function order(product, sizeId, qtyId, customId){
const size = parseFloat(document.getElementById(sizeId).value);
const qtySelect = document.getElementById(qtyId).value;
const customQty = document.getElementById(customId).value;

const qty = (qtySelect === "custom" && customQty) ? parseInt(customQty) : parseInt(qtySelect);

const discount = getDiscount(qty);
const total = (pricePerOz * size * qty) * (1 - discount);

const msg = "DIABLITO\n\nOrder Request\n\n" +
product + "\n" +
"Size: " + sizeLabel(size) + "\n" +
"Quantity: " + qty + "\n" +
"Total: $" + total.toFixed(2) + "\n" +
"Please confirm availability and total.\n\n";

window.open("https://wa.me/526635130363?text=" + encodeURIComponent(msg));
}
</script>

</body>
</html>
