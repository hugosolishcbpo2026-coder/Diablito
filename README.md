<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Diablito Smoke Shop</title>

<style>
:root {
  --bg:#111;
  --accent:#d00000;
  --text:#eee;
  --card:#222;
  --highlight:#ff6600;
}

body {
  margin:0;
  font-family:"Segoe UI",sans-serif;
  background:var(--bg);
  color:var(--text);
}

/* HEADER */
header {
  background:var(--accent);
  padding:20px;
  text-align:center;
}
header h1 {
  margin:0;
  font-size:2.5rem;
}
nav a {
  color:#fff;
  margin:0 15px;
  text-decoration:none;
  font-weight:bold;
}

/* HERO */
.hero {
  text-align:center;
  padding:60px 20px;
  background:linear-gradient(135deg,var(--accent),var(--highlight));
}
.hero button {
  background:#000;
  color:#fff;
  border:none;
  padding:15px 30px;
  cursor:pointer;
}

/* PRODUCTS */
.products {
  display:flex;
  flex-wrap:wrap;
  gap:20px;
  justify-content:center;
  padding:40px 20px;
}
.product-card {
  background:var(--card);
  border-radius:10px;
  padding:20px;
  width:250px;
  text-align:center;
}
.product-card img {
  width:100%;
  border-radius:8px;
}
.product-card button {
  background:var(--accent);
  color:#fff;
  border:none;
  padding:10px;
  cursor:pointer;
}

/* CART */
.cart {
  position:fixed;
  top:10px;
  right:10px;
  background:#000;
  padding:15px;
  border-radius:10px;
}
.cart h4 {
  margin:0 0 10px 0;
}
</style>
</head>

<body>

<header>
  <h1>🔥 Diablito Smoke Shop</h1>
  <nav>
    <a href="#products">Products</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<section class="hero">
  <h2>Premium Smoke & Accessories</h2>
  <p>Unique products. Real quality. No bullshit.</p>
  <button onclick="scrollToProducts()">Shop Now</button>
</section>

<!-- CART -->
<div class="cart">
  <h4>🛒 Cart</h4>
  <div id="cart-items"></div>
  <strong>Total: $<span id="total">0</span></strong>
</div>

<!-- PRODUCTS -->
<section id="products" class="products">

  <div class="product-card">
    <img src="https://via.placeholder.com/250" alt="">
    <h3>Glass Pipe</h3>
    <p>$25</p>
    <button onclick="addToCart('Glass Pipe',25)">Add to Cart</button>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/250" alt="">
    <h3>Rolling Papers</h3>
    <p>$5</p>
    <button onclick="addToCart('Rolling Papers',5)">Add to Cart</button>
  </div>

  <div class="product-card">
    <img src="https://via.placeholder.com/250" alt="">
    <h3>Grinder</h3>
    <p>$15</p>
    <button onclick="addToCart('Grinder',15)">Add to Cart</button>
  </div>

</section>

<section id="about" style="text-align:center;padding:40px;">
  <h2>About</h2>
  <p>Tijuana-based smoke shop bringing premium gear and street culture together.</p>
</section>

<section id="contact" style="text-align:center;padding:40px;">
  <h2>Contact</h2>
  <p>Email: info@diablito.com</p>
</section>

<footer style="text-align:center;padding:20px;background:#000;">
  <p>© 2026 Diablito Smoke Shop</p>
</footer>

<script>
let cart = [];
let total = 0;

function scrollToProducts() {
  document.getElementById("products").scrollIntoView({behavior:"smooth"});
}

function addToCart(name, price) {
  cart.push({name, price});
  total += price;
  renderCart();
}

function renderCart() {
  const cartItems = document.getElementById("cart-items");
  cartItems.innerHTML = "";

  cart.forEach(item => {
    const div = document.createElement("div");
    div.textContent = item.name + " - $" + item.price;
    cartItems.appendChild(div);
  });

  document.getElementById("total").textContent = total;
}
</script>

</body>
</html>
