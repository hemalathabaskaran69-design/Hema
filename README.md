<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>PureHarvest — Organic Snacks</title>
  <meta name="description" content="PureHarvest — Healthy organic snacks made from natural ingredients. Nuts, granola, dried fruits and more." />

  <!-- Basic styling (embedded for single-file use) -->
  <style>
    :root{
      --accent:#2f7a3e;
      --accent-2:#6bb77b;
      --muted:#6b6b6b;
      --bg:#fbfbf8;
      --card:#ffffff;
      --radius:14px;
      --max-width:1100px;
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }

    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      background:linear-gradient(180deg,#fbfff8 0%, #f6f8f6 100%);
      color:#0b1a12;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.45;
    }

    .container{max-width:var(--max-width);margin:0 auto;padding:24px;}

    /* Header */
    header{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:16px;
      margin-bottom:28px;
    }
    .brand{
      display:flex;
      align-items:center;
      gap:12px;
      text-decoration:none;
      color:inherit;
    }
    .logo{
      width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,var(--accent),var(--accent-2));
      display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:20px;
      box-shadow:0 6px 18px rgba(47,122,62,0.15);
    }
    nav.desktop{display:flex;gap:16px;align-items:center;}
    nav.desktop a{color:var(--muted);text-decoration:none;padding:8px;border-radius:8px;}
    nav.desktop a:hover{background:rgba(47,122,62,0.06);color:var(--accent)}
    .cta{
      background:var(--accent);
      color:white;padding:10px 14px;border-radius:10px;text-decoration:none;font-weight:600;
      box-shadow:0 6px 18px rgba(47,122,62,0.12);
    }

    /* Mobile nav toggle */
    .mobile-toggle{display:none;background:none;border:0;font-size:20px;padding:8px;border-radius:8px}

    /* Hero */
    .hero{
      display:grid;
      grid-template-columns:1fr 420px;
      gap:28px;
      align-items:center;
      margin-bottom:36px;
    }
    .hero-left h1{font-size:32px;margin:0 0 12px}
    .hero-left p{color:var(--muted);margin:0 0 18px}
    .hero-cta{display:flex;gap:12px}
    .pill{display:inline-flex;gap:8px;align-items:center;background:#e9f6ec;padding:8px 12px;border-radius:999px;color:var(--accent);font-weight:600;font-size:13px}

    .hero-right{
      background:linear-gradient(180deg, rgba(255,255,255,0.5), rgba(255,255,255,0.6));
      padding:18px;border-radius:18px;box-shadow:0 8px 30px rgba(15,30,15,0.06);
    }
    .product-sample{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
    .sample-card{background:var(--card);padding:10px;border-radius:12px;display:flex;gap:12px;align-items:center}
    .sample-card img{width:72px;height:72px;border-radius:10px;object-fit:cover}

    /* Products grid */
    .section{margin:40px 0}
    .grid{
      display:grid;
      grid-template-columns:repeat(3,1fr);
      gap:18px;
    }
    .card{background:var(--card);padding:14px;border-radius:16px;box-shadow:0 6px 20px rgba(20,35,20,0.04);display:flex;flex-direction:column;gap:12px}
    .card img{width:100%;height:160px;object-fit:cover;border-radius:10px}
    .price{font-weight:700;color:var(--accent)}
    .tag{font-size:12px;padding:6px 10px;border-radius:999px;background:#f0f7f1;color:var(--accent);display:inline-block}

    /* About & contact */
    .two-col{display:grid;grid-template-columns:1fr 1fr;gap:24px;align-items:center}
    .contact-form input,.contact-form textarea{
      width:100%;padding:10px;border-radius:10px;border:1px solid #e6ece6;margin-bottom:10px;font-size:14px;
    }

    footer{margin-top:36px;padding:24px 0;color:var(--muted);font-size:14px;border-top:1px solid #eef5ee}

    /* Responsive */
    @media (max-width:980px){
      .hero{grid-template-columns:1fr}
      .grid{grid-template-columns:repeat(2,1fr)}
    }
    @media (max-width:680px){
      header{padding:0 8px}
      .mobile-toggle{display:inline-flex}
      nav.desktop{display:none}
      .hero-right{order:2}
      .hero-left{order:1}
      .grid{grid-template-columns:1fr}
      .two-col{grid-template-columns:1fr}
    }

    /* small helper */
    .muted{color:var(--muted)}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <a class="brand" href="#">
        <div class="logo">PH</div>
        <div>
          <div style="font-weight:700">PureHarvest</div>
          <div class="muted" style="font-size:13px">Organic snacks & wholesome bites</div>
        </div>
      </a>

      <nav class="desktop" aria-label="Main navigation">
        <a href="#products">Products</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
        <a class="cta" href="#products">Shop Now</a>
      </nav>

      <button class="mobile-toggle" aria-expanded="false" aria-controls="mobileMenu" id="mobileToggle">☰</button>
    </header>

    <!-- Mobile menu (hidden on desktop) -->
    <div id="mobileMenu" style="display:none;margin-bottom:18px">
      <nav style="display:flex;flex-direction:column;gap:8px">
        <a href="#products">Products</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>

    <!-- Hero -->
    <section class="hero" aria-labelledby="hero-heading">
      <div class="hero-left">
        <div class="pill">100% Organic</div>
        <h1 id="hero-heading">Healthy snacks. Honest ingredients.</h1>
        <p class="muted">Discover crunchy roasted nuts, gluten-free granola, and naturally dried fruits — made with care and no nasties.</p>

        <div class="hero-cta">
          <a class="cta" href="#products">Browse Snacks</a>
          <a href="#about" style="padding:10px 14px;border-radius:10px;background:transparent;border:1px solid #e6efe6;text-decoration:none;color:var(--accent);font-weight:600">Our Story</a>
        </div>

        <ul style="margin-top:18px;color:var(--muted);font-size:14px;padding-left:18px">
          <li>Locally sourced</li>
          <li>No added sugar</li>
          <li>Sustainably packaged</li>
        </ul>
      </div>

      <aside class="hero-right" aria-hidden="false">
        <div style="font-weight:700;margin-bottom:8px">Featured sampler</div>
        <div class="product-sample">
          <div class="sample-card">
            <img src="https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=800&q=60" alt="Mixed nuts"/>
            <div>
              <div style="font-weight:700">Roasted Nuts</div>
              <div class="muted" style="font-size:13px">Salt-free, flavor-packed</div>
            </div>
          </div>

          <div class="sample-card">
            <img src="https://images.unsplash.com/photo-1506806732259-39c2d0268443?auto=format&fit=crop&w=800&q=60" alt="Granola"/>
            <div>
              <div style="font-weight:700">Honey Granola</div>
              <div class="muted" style="font-size:13px">Crunchy & wholesome</div>
            </div>
          </div>

          <div class="sample-card">
            <img src="https://images.unsplash.com/photo-1604908177116-2d0b8cf244d4?auto=format&fit=crop&w=800&q=60" alt="Dried fruit"/>
            <div>
              <div style="font-weight:700">Dried Mango</div>
              <div class="muted" style="font-size:13px">Naturally sweet</div>
            </div>
          </div>

          <div class="sample-card">
            <img src="https://images.unsplash.com/photo-1565895405136-7c6d1fdc34ca?auto=format&fit=crop&w=800&q=60" alt="Trail mix"/>
            <div>
              <div style="font-weight:700">Trail Mix</div>
              <div class="muted" style="font-size:13px">Energy on-the-go</div>
            </div>
          </div>
        </div>
      </aside>
    </section>

    <!-- Products -->
    <section id="products" class="section">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:16px">
        <h2 style="margin:0">Our Bestsellers</h2>
        <div class="muted">Free shipping on orders ₹1,200+</div>
      </div>

      <div class="grid" role="list">
        <!-- Product card -->
        <article class="card" role="listitem" tabindex="0">
          <img src="https://images.unsplash.com/photo-1505577058444-a3dab5bff3f3?auto=format&fit=crop&w=1200&q=60" alt="Almonds - roasted"/>
          <div style="display:flex;justify-content:space-between;align-items:center">
            <div style="font-weight:700">Roasted Almonds</div>
            <div class="price">₹450</div>
          </div>
          <div class="muted" style="font-size:14px">Crunchy, lightly roasted almonds — rich in protein and healthy fats.</div>
          <div style="display:flex;gap:8px;margin-top:auto">
            <button onclick="openProduct('Roasted Almonds','₹450','Crunchy, lightly roasted almonds — rich in protein and healthy fats.','https://images.unsplash.com/photo-1505577058444-a3dab5bff3f3?auto=format&fit=crop&w=1200&q=60')" style="padding:10px 12px;border-radius:10px;border:0;background:#f0f6f1">Details</button>
            <button style="padding:10px 12px;border-radius:10px;border:0;background:var(--accent);color:white">Add to cart</button>
          </div>
        </article>

        <article class="card" role="listitem" tabindex="0">
          <img src="https://images.unsplash.com/photo-1542444459-db9a8f7d0441?auto=format&fit=crop&w=1200&q=60" alt="Granola jar"/>
          <div style="display:flex;justify-content:space-between;align-items:center">
            <div style="font-weight:700">Crispy Granola</div>
            <div class="price">₹320</div>
          </div>
          <div class="muted" style="font-size:14px">Made with oats, seeds and a touch of honey — perfect with yogurt.</div>
          <div style="display:flex;gap:8px;margin-top:auto">
            <button onclick="openProduct('Crispy Granola','₹320','Made with oats, seeds and a touch of honey — perfect with yogurt.','https://images.unsplash.com/photo-1542444459-db9a8f7d0441?auto=format&fit=crop&w=1200&q=60')" style="padding:10px 12px;border-radius:10px;border:0;background:#f0f6f1">Details</button>
            <button style="padding:10px 12px;border-radius:10px;border:0;background:var(--accent);color:white">Add to cart</button>
          </div>
        </article>

        <article class="card" role="listitem" tabindex="0">
          <img src="https://images.unsplash.com/photo-1604908177116-2d0b8cf244d4?auto=format&fit=crop&w=1200&q=60" alt="Dried mango"/>
          <div style="display:flex;justify-content:space-between;align-items:center">
            <div style="font-weight:700">Dried Mango</div>
            <div class="price">₹210</div>
          </div>
          <div class="muted" style="font-size:14px">Naturally dried — no added sugar, soft and chewy slices.</div>
          <div style="display:flex;gap:8px;margin-top:auto">
            <button onclick="openProduct('Dried Mango','₹210','Naturally dried — no added sugar, soft and chewy slices.','https://images.unsplash.com/photo-1604908177116-2d0b8cf244d4?auto=format&fit=crop&w=1200&q=60')" style="padding:10px 12px;border-radius:10px;border:0;background:#f0f6f1">Details</button>
            <button style="padding:10px 12px;border-radius:10px;border:0;background:var(--accent);color:white">Add to cart</button>
          </div>
        </article>

        <article class="card" role="listitem" tabindex="0">
          <img src="https://images.unsplash.com/photo-1550258987-190a2d41a8ba?auto=format&fit=crop&w=1200&q=60" alt="Trail mix"/>
          <div style="display:flex;justify-content:space-between;align-items:center">
            <div style="font-weight:700">Trail Mix</div>
            <div class="price">₹350</div>
          </div>
          <div class="muted" style="font-size:14px">A balanced mix of nuts, seeds and dried fruit — great for hikes.</div>
          <div style="display:flex;gap:8px;margin-top:auto">
            <button onclick="openProduct('Trail Mix','₹350','A balanced mix of nuts, seeds and dried fruit — great for hikes.','https://images.unsplash.com/photo-1550258987-190a2d41a8ba?auto=format&fit=crop&w=1200&q=60')" style="padding:10px 12px;border-radius:10px;border:0;background:#f0f6f1">Details</button>
            <button style="padding:10px 12px;border-radius:10px;border:0;background:var(--accent);color:white">Add to cart</button>
          </div>
        </article>

        <article class="card" role="listitem" tabindex="0">
          <img src="https://images.unsplash.com/photo-1492684223066-81342ee5ff30?auto=format&fit=crop&w=1200&q=60" alt="Pumpkin seeds"/>
          <div style="display:flex;justify-content:space-between;align-items:center">
            <div style="font-weight:700">Pumpkin Seeds</div>
            <div class="price">₹280</div>
          </div>
          <div class="muted" style="font-size:14px">Lightly toasted seeds — rich in zinc and iron.</div>
          <div style="display:flex;gap:8px;margin-top:auto">
            <button onclick="openProduct('Pumpkin Seeds','₹280','Lightly toasted seeds — rich in zinc and iron.','https://images.unsplash.com/photo-1492684223066-81342ee5ff30?auto=format&fit=crop&w=1200&q=60')" style="padding:10px 12px;border-radius:10px;border:0;background:#f0f6f1">Details</button>
            <button style="padding:10px 12px;border-radius:10px;border:0;background:var(--accent);color:white">Add to cart</button>
          </div>
        </article>

        <article class="card" role="listitem" tabindex="0">
          <img src="https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=60" alt="Cashew snack"/>
          <div style="display:flex;justify-content:space-between;align-items:center">
            <div style="font-weight:700">Spiced Cashews</div>
            <div class="price">₹420</div>
          </div>
          <div class="muted" style="font-size:14px">Hand-spiced cashews with a mild smoky flavor.</div>
          <div style="display:flex;gap:8px;margin-top:auto">
            <button onclick="openProduct('Spiced Cashews','₹420','Hand-spiced cashews with a mild smoky flavor.','https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=60')" style="padding:10px 12px;border-radius:10px;border:0;background:#f0f6f1">Details</button>
            <button style="padding:10px 12px;border-radius:10px;border:0;background:var(--accent);color:white">Add to cart</button>
          </div>
        </article>
      </div>
    </section>

    <!-- About & contact -->
    <section id="about" class="section">
      <div style="display:flex;justify-content:space-between;align-items:center;gap:24px;flex-wrap:wrap">
        <div style="flex:1;min-width:260px">
          <h2>About PureHarvest</h2>
          <p class="muted">We work with responsible farmers to source the best organic produce. Our snacks are minimal-ingredient, freshly packed and shipped in recyclable pouches.</p>
          <ul style="margin-top:12px;color:var(--muted)">
            <li>Certified organic ingredients</li>
            <li>No artificial flavors or preservatives</li>
            <li>Small-batch roasting</li>
          </ul>
        </div>

        <div style="flex:1;min-width:260px">
          <h3>Why choose us</h3>
          <div style="display:flex;gap:10px;flex-direction:column">
            <div style="display:flex;gap:12px;align-items:flex-start">
              <div class="tag">100% Traceable</div>
              <div><strong>Transparent sourcing</strong><div class="muted" style="font-size:13px">We share origin details for every product.</div></div>
            </div>
            <div style="display:flex;gap:12px;align-items:flex-start">
              <div class="tag">Eco Pack</div>
              <div><strong>Recyclable</strong><div class="muted" style="font-size:13px">Minimal plastic use and compostable options.</div></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="contact" class="section">
      <h2>Get in touch</h2>
      <div class="two-col">
        <div class="contact-form">
          <label for="name" class="muted">Name</label>
          <input id="name" placeholder="Your name" />
          <label for="email" class="muted">Email</label>
          <input id="email" placeholder="you@example.com" />
          <label for="message" class="muted">Message</label>
          <textarea id="message" rows="4" placeholder="How can we help?"></textarea>
          <button class="cta" onclick="alert('Thanks — we will reply soon!')">Send Message</button>
        </div>

        <div>
          <h3>Visit our kitchen</h3>
          <p class="muted">123 Green Lane, Bangalore, India</p>
          <p class="muted">Mon — Fri: 9:00 — 18:00</p>
          <div style="margin-top:12px">
            <strong>Follow us</strong>
            <div style="display:flex;gap:10px;margin-top:8px">
              <a class="tag" href="#" aria-label="Instagram">IG</a>
              <a class="tag" href="#" aria-label="Facebook">FB</a>
              <a class="tag" href="#" aria-label="X">X</a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <footer>
      <div style="display:flex;justify-content:space-between;flex-wrap:wrap;gap:12px">
        <div>© <strong>PureHarvest</strong> 2025 • All rights reserved.</div>
        <div class="muted">Made with care • Terms • Privacy</div>
      </div>
    </footer>
  </div>

  <!-- Product modal (simple) -->
  <div id="productModal" style="display:none;position:fixed;inset:0;align-items:center;justify-content:center;background:rgba(0,0,0,0.5);padding:20px;">
    <div style="background:white;border-radius:14px;max-width:720px;width:100%;padding:18px;box-shadow:0 20px 50px rgba(10,20,10,0.4);position:relative">
      <button onclick="closeModal()" style="position:absolute;right:14px;top:12px;background:none;border:0;font-size:18px">✕</button>
      <div id="modalContent" style="display:grid;grid-template-columns:1fr 1fr;gap:12px;align-items:center">
        <div>
          <img id="modalImg" src="" alt="" style="width:100%;height:260px;object-fit:cover;border-radius:10px" />
        </div>
        <div>
          <h3 id="modalTitle" style="margin-top:0"></h3>
          <div id="modalPrice" style="font-weight:700;color:var(--accent);margin-bottom:8px"></div>
          <p id="modalDesc" class="muted"></p>
          <div style="margin-top:12px">
            <button style="padding:10px 12px;border-radius:10px;border:0;background:var(--accent);color:white">Add to cart</button>
            <button onclick="closeModal()" style="padding:10px 12px;border-radius:10px;border:0;background:#f0f6f1;margin-left:8px">Close</button>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Minimal JS -->
  <script>
    const mobileToggle = document.getElementById('mobileToggle');
    const mobileMenu = document.getElementById('mobileMenu');
    mobileToggle.addEventListener('click', () => {
      const open = mobileMenu.style.display === 'block';
      mobileMenu.style.display = open ? 'none' : 'block';
      mobileToggle.setAttribute('aria-expanded', String(!open));
    });

    function openProduct(title, price, desc, img) {
      document.getElementById('modalTitle').textContent = title;
      document.getElementById('modalPrice').textContent = price;
      document.getElementById('modalDesc').textContent = desc;
      document.getElementById('modalImg').src = img;
      document.getElementById('productModal').style.display = 'flex';
      document.body.style.overflow = 'hidden';
    }
    function closeModal() {
      document.getElementById('productModal').style.display = 'no
