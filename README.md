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
    header {
      background:var(--accent);
      padding:20px;
      text-align:center;
    }
    header h1 {
      margin:0;
      font-size:2.5rem;
      color:#fff;
      text-shadow:0 0 10px #ff4444;
    }
    nav {
      margin-top:10px;
    }
    nav a {
      color:#fff;
      margin:0 15px;
      text-decoration:none;
      font-weight:bold;
    }
    .hero {
      text-align:center;
      padding:60px 20px;
      background:linear-gradient(135deg,var(--accent),var(--highlight));
    }
    .hero h2 {
      font-size:2rem;
      margin-bottom:20px;
    }
    .hero p {
      max-width:600px;
      margin:0 auto 20px;
    }
    .hero button {
      background:#000;
      color:#fff;
      border:none;
      padding:15px 30px;
      font-size:1em;
      cursor:pointer;
    }
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
      box-shadow:0 0 10px rgba(255,0,0,0.3);
    }
    .product-card img {
      width:100%;
      border-radius:8px;
      margin-bottom:10px;
    }
    .product-card h3 {
      margin:10px 0;
      color:var(--highlight);
    }
    .product-card p {
      margin:5px 0;
    }
    .product-card button {
      background:var(--accent);
      color:#fff;
      border:none;
      padding:10px 20px;
      cursor:pointer;
    }
    footer {
      background:#000;
      color:#999;
      text-align:center;
      padding:20px;
      margin-top:40px;
    }
  </style>
</head>
<body>

<header>
  <h1>Diablito Smoke Shop</h1>
  <nav>
    <a href="#products">Products</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<section class="hero">
  <h2>Premium Smoke & Accessories</h2>
  <p>Discover unique products and exclusive deals at Diablito.</p>
  <button>Shop Now</button>
</section>

<section id="products" class="products">
  <!-- Product placeholders -->
  <div class="product-card">
    <img src="placeholder.jpg" alt="Product Image">
    <h3>Product Name</h3>
    <p>$[Price]</p>
    <button>Add to Cart</button>
  </div>
  <div class="product-card">
    <img src="placeholder.jpg" alt="Product Image">
    <h3>Product Name</h3>
    <p>$[Price]</p>
    <button>Add to Cart</button>
  </div>
  <div class="product-card">
    <img src="placeholder.jpg" alt="Product Image">
    <h3>Product Name</h3>
    <p>$[Price]</p>
    <button>Add to Cart</button>
  </div>
</section>

<section id="about" style="padding:40px 20px;text-align:center;">
  <h2>About Diablito</h2>
  <p>We are a Tijuana‑based smoke shop offering premium products, accessories, and a unique shopping experience.</p>
</section>

<section id="contact" style="padding:40px 20px;text-align:center;">
  <h2>Contact Us</h2>
  <p>Email: info@diablito.com | Phone: (123) 456‑7890</p>
</section>

<footer>
  <p>&copy; 2026 Diablito Smoke Shop. All rights reserved.</p>
</footer>

</body>
</html>
