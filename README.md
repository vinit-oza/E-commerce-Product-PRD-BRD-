<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ShopSphere — Wireframes | Project Horizon</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Archivo:wght@400;500;600;700;800&family=Spline+Sans+Mono:wght@400;500;600&display=swap');

  :root{
    --ink:#14202e; --line:#9aa7b4; --line-strong:#3d566e; --paper:#f4f1ea;
    --panel:#ffffff; --ph:#dfe4ea; --ph-line:#c2cbd4; --accent:#1f5fa8;
    --accent-soft:#dbe6f3; --note:#b4531f; --note-soft:#f6e3d4; --ok:#3d7a45;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  body{
    font-family:'Archivo',sans-serif; color:var(--ink); background:var(--paper);
    background-image:linear-gradient(rgba(61,86,110,.05) 1px,transparent 1px),
                     linear-gradient(90deg,rgba(61,86,110,.05) 1px,transparent 1px);
    background-size:22px 22px; line-height:1.45; padding:0 0 80px;
  }
  .wrap{max-width:1180px;margin:0 auto;padding:0 28px;}

  /* ---- Masthead ---- */
  header.mast{border-bottom:3px solid var(--ink);margin-bottom:34px;padding:42px 0 26px;}
  .mast .wrap{display:flex;justify-content:space-between;align-items:flex-end;gap:24px;flex-wrap:wrap;}
  .mast h1{font-size:34px;font-weight:800;letter-spacing:-.5px;line-height:1;}
  .mast h1 span{color:var(--accent);}
  .mast .sub{font-family:'Spline Sans Mono',monospace;font-size:12px;color:var(--line-strong);margin-top:10px;text-transform:uppercase;letter-spacing:1.5px;}
  .stamp{font-family:'Spline Sans Mono',monospace;font-size:11px;text-align:right;color:var(--line-strong);
         border:1.5px solid var(--line-strong);padding:10px 14px;border-radius:3px;background:var(--panel);}
  .stamp b{color:var(--ink);}

  /* ---- index strip ---- */
  .index{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:38px;}
  .index a{font-family:'Spline Sans Mono',monospace;font-size:11px;text-decoration:none;color:var(--ink);
    border:1.5px solid var(--line);padding:7px 12px;border-radius:3px;background:var(--panel);transition:.15s;}
  .index a:hover{background:var(--ink);color:#fff;border-color:var(--ink);}

  /* ---- screen blocks ---- */
  .screen{margin-bottom:52px;scroll-margin-top:20px;}
  .screen-head{display:flex;align-items:baseline;gap:14px;margin-bottom:14px;border-bottom:1.5px dashed var(--line-strong);padding-bottom:8px;flex-wrap:wrap;}
  .screen-no{font-family:'Spline Sans Mono',monospace;font-weight:600;font-size:13px;color:#fff;background:var(--accent);padding:3px 9px;border-radius:3px;}
  .screen-head h2{font-size:20px;font-weight:700;letter-spacing:-.2px;}
  .screen-head .ref{font-family:'Spline Sans Mono',monospace;font-size:11px;color:var(--note);margin-left:auto;}

  .frame{border:2px solid var(--line-strong);background:var(--panel);border-radius:6px;overflow:hidden;
         box-shadow:6px 6px 0 rgba(20,32,46,.08);}
  .browser-bar{display:flex;align-items:center;gap:7px;padding:9px 14px;background:#e9eef3;border-bottom:1.5px solid var(--line);}
  .dot{width:11px;height:11px;border-radius:50%;border:1.5px solid var(--line-strong);}
  .url{flex:1;margin-left:10px;font-family:'Spline Sans Mono',monospace;font-size:11px;color:var(--line-strong);
       background:#fff;border:1.5px solid var(--line);border-radius:20px;padding:4px 14px;}
  .canvas{padding:18px;}

  /* wireframe primitives */
  .box{border:1.5px solid var(--ph-line);background:var(--ph);border-radius:4px;}
  .ph{position:relative;border:1.5px solid var(--ph-line);background:
        repeating-linear-gradient(135deg,#e7ebf0,#e7ebf0 9px,#dfe4ea 9px,#dfe4ea 18px);
      border-radius:4px;display:flex;align-items:center;justify-content:center;
      font-family:'Spline Sans Mono',monospace;font-size:10px;color:#8a97a4;text-transform:uppercase;letter-spacing:1px;min-height:46px;}
  .lbl{font-family:'Spline Sans Mono',monospace;font-size:10px;color:#8a97a4;text-transform:uppercase;letter-spacing:1px;}
  .txtline{height:8px;background:var(--ph-line);border-radius:3px;margin:5px 0;}
  .txtline.s{width:55%;} .txtline.m{width:75%;} .txtline.xs{width:35%;}
  .btn{display:inline-flex;align-items:center;justify-content:center;border:1.5px solid var(--line-strong);
       border-radius:4px;font-size:11px;font-weight:600;padding:8px 14px;color:var(--ink);background:#fff;}
  .btn.fill{background:var(--accent);color:#fff;border-color:var(--accent);}
  .row{display:flex;gap:12px;} .col{flex:1;}
  .pill{border:1.5px solid var(--line);border-radius:20px;padding:5px 12px;font-size:11px;color:var(--line-strong);background:#fff;display:inline-block;}

  /* annotation badge */
  .anno{display:inline-flex;align-items:center;justify-content:center;min-width:19px;height:19px;padding:0 4px;
        background:var(--note);color:#fff;border-radius:50%;font-family:'Spline Sans Mono',monospace;
        font-size:11px;font-weight:600;vertical-align:middle;margin-left:5px;}
  .notes{margin-top:14px;border:1.5px solid var(--note);background:var(--note-soft);border-radius:5px;padding:14px 16px;}
  .notes h4{font-family:'Spline Sans Mono',monospace;font-size:11px;text-transform:uppercase;letter-spacing:1.5px;color:var(--note);margin-bottom:9px;}
  .notes ul{list-style:none;display:grid;grid-template-columns:1fr 1fr;gap:6px 26px;}
  .notes li{font-size:12.5px;display:flex;gap:8px;align-items:flex-start;}
  .notes .n{flex-shrink:0;width:18px;height:18px;background:var(--note);color:#fff;border-radius:50%;
            font-family:'Spline Sans Mono',monospace;font-size:10px;display:flex;align-items:center;justify-content:center;margin-top:1px;}
  .notes code{font-family:'Spline Sans Mono',monospace;font-size:11px;color:var(--accent);background:#fff;padding:1px 5px;border-radius:3px;border:1px solid var(--accent-soft);}

  /* header/nav inside frames */
  .topnav{display:flex;align-items:center;gap:16px;padding:12px 14px;border:1.5px solid var(--ph-line);border-radius:4px;background:#fff;}
  .logo{font-weight:800;font-size:15px;color:var(--accent);} .logo b{color:var(--ink);}
  .search{flex:1;display:flex;align-items:center;border:1.5px solid var(--line);border-radius:5px;padding:8px 12px;font-size:11px;color:#8a97a4;font-family:'Spline Sans Mono',monospace;}
  .navicons{display:flex;gap:10px;} .navicons .box{width:30px;height:30px;}

  .catnav{display:flex;gap:8px;flex-wrap:wrap;margin-top:10px;}
  .catnav .pill{font-size:10.5px;}

  .grid4{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;}
  .grid3{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;}
  .grid2{display:grid;grid-template-columns:repeat(2,1fr);gap:12px;}
  .card{border:1.5px solid var(--ph-line);border-radius:5px;padding:10px;background:#fff;}
  .card .price{font-weight:700;font-size:13px;margin-top:6px;}
  .card .star{font-size:10px;color:var(--note);font-family:'Spline Sans Mono',monospace;}

  /* phone frames */
  .phones{display:flex;gap:26px;flex-wrap:wrap;justify-content:center;}
  .phone{width:230px;border:2.5px solid var(--ink);border-radius:26px;padding:10px 9px;background:var(--panel);box-shadow:5px 5px 0 rgba(20,32,46,.08);}
  .phone .notch{width:70px;height:6px;background:var(--ink);border-radius:6px;margin:2px auto 9px;}
  .phone .pscreen{border:1.5px solid var(--ph-line);border-radius:14px;padding:10px;min-height:380px;background:#fff;}
  .phone .cap{text-align:center;font-family:'Spline Sans Mono',monospace;font-size:10px;color:var(--line-strong);margin-top:9px;text-transform:uppercase;letter-spacing:1px;}
  .tabbar{display:flex;justify-content:space-around;border-top:1.5px solid var(--ph-line);padding-top:8px;margin-top:10px;}
  .tabbar .box{width:24px;height:24px;}

  .footnote{font-family:'Spline Sans Mono',monospace;font-size:11px;color:var(--line-strong);
            border-top:3px solid var(--ink);margin-top:30px;padding-top:18px;display:flex;justify-content:space-between;flex-wrap:wrap;gap:10px;}
  .legend{display:flex;gap:18px;flex-wrap:wrap;margin-bottom:30px;font-family:'Spline Sans Mono',monospace;font-size:11px;color:var(--line-strong);}
  .legend span{display:inline-flex;align-items:center;gap:7px;}
  .sw{width:22px;height:14px;border-radius:3px;border:1.5px solid var(--ph-line);}
  @media(max-width:760px){.notes ul{grid-template-columns:1fr;}.grid4{grid-template-columns:repeat(2,1fr);}.mast h1{font-size:26px;}}
</style>
</head>
<body>

<header class="mast">
  <div class="wrap">
    <div>
      <h1>Shop<span>Sphere</span> — Wireframe Set</h1>
      <div class="sub">Project Horizon · Meridian Retail Pvt. Ltd. · Low-Fidelity UX Blueprint v1.0</div>
    </div>
    <div class="stamp">
      DOC&nbsp;: WF-SHS-001<br>
      OWNER&nbsp;: UX / BA<br>
      STATUS&nbsp;: <b>FOR REVIEW</b><br>
      LINKED&nbsp;: FRD &amp; SRS
    </div>
  </div>
</header>

<div class="wrap">

  <div class="legend">
    <span><span class="sw" style="background:repeating-linear-gradient(135deg,#e7ebf0,#e7ebf0 5px,#dfe4ea 5px,#dfe4ea 10px)"></span> Image / media placeholder</span>
    <span><span class="sw" style="background:#dfe4ea"></span> Content block</span>
    <span><span class="sw" style="background:#1f5fa8;border-color:#1f5fa8"></span> Primary action</span>
    <span><span class="anno" style="position:static;margin:0">N</span> Annotation → maps to FRD requirement</span>
  </div>

  <nav class="index">
    <a href="#s1">01 · Home</a>
    <a href="#s2">02 · Listing (PLP)</a>
    <a href="#s3">03 · Product (PDP)</a>
    <a href="#s4">04 · Cart</a>
    <a href="#s5">05 · Checkout</a>
    <a href="#s6">06 · Account / Orders</a>
    <a href="#s7">07 · Admin & Supply Chain</a>
    <a href="#s8">08 · Mobile App</a>
  </nav>

  <!-- 01 HOME -->
  <section class="screen" id="s1">
    <div class="screen-head"><span class="screen-no">01</span><h2>Homepage</h2><span class="ref">FRD-2.x · Discovery & Merchandising</span></div>
    <div class="frame">
      <div class="browser-bar"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="url">https://www.shopsphere.in/</span></div>
      <div class="canvas">
        <div class="topnav">
          <span class="logo">Shop<b>Sphere</b></span>
          <span class="search">⌕ &nbsp;Search products, brands &amp; categories<span class="anno">1</span></span>
          <div class="navicons"><span class="lbl">EN/हिं<span class="anno">2</span></span><span class="box"></span><span class="box"></span><span class="box"></span></div>
        </div>
        <div class="catnav">
          <span class="pill">Electronics</span><span class="pill">Fashion</span><span class="pill">Home</span>
          <span class="pill">Grocery</span><span class="pill">Beauty</span><span class="pill">Offers</span><span class="pill">Sell on ShopSphere</span>
        </div>
        <div style="margin-top:14px" class="ph" >Hero / Promotional Banner Carousel <span class="anno">3</span></div>
        <div style="height:90px"></div>
        <div class="lbl" style="margin:14px 0 8px">Shop by Category</div>
        <div class="grid4">
          <div class="ph" style="height:80px">Category</div><div class="ph" style="height:80px">Category</div>
          <div class="ph" style="height:80px">Category</div><div class="ph" style="height:80px">Category</div>
        </div>
        <div class="lbl" style="margin:16px 0 8px">Recommended for You <span class="anno">4</span></div>
        <div class="grid4">
          <div class="card"><div class="ph" style="height:70px">Product</div><div class="txtline m"></div><div class="txtline s"></div><div class="price">₹ —</div><div class="star">★★★★☆</div></div>
          <div class="card"><div class="ph" style="height:70px">Product</div><div class="txtline m"></div><div class="txtline s"></div><div class="price">₹ —</div><div class="star">★★★★★</div></div>
          <div class="card"><div class="ph" style="height:70px">Product</div><div class="txtline m"></div><div class="txtline s"></div><div class="price">₹ —</div><div class="star">★★★★☆</div></div>
          <div class="card"><div class="ph" style="height:70px">Product</div><div class="txtline m"></div><div class="txtline s"></div><div class="price">₹ —</div><div class="star">★★★☆☆</div></div>
        </div>
        <div style="margin-top:16px" class="ph">Footer · Policies · Support · App download · Trust badges <span class="anno">5</span></div>
        <div style="height:30px"></div>
      </div>
    </div>
    <div class="notes">
      <h4>Annotations</h4>
      <ul>
        <li><span class="n">1</span><div>Predictive search with auto-suggest, recent &amp; trending queries — <code>FRD-2.1</code></div></li>
        <li><span class="n">2</span><div>Locale toggle (EN / Hindi) &amp; currency in INR — <code>SRS-NFR-Usability</code></div></li>
        <li><span class="n">3</span><div>CMS-managed merchandising banners, scheduled campaigns — <code>FRD-2.4</code></div></li>
        <li><span class="n">4</span><div>Personalized recommendations from behaviour model — <code>FRD-2.5</code></div></li>
        <li><span class="n">5</span><div>Trust signals: secure-payment, return policy, ratings — <code>FRD-9.x</code></div></li>
      </ul>
    </div>
  </section>

  <!-- 02 PLP -->
  <section class="screen" id="s2">
    <div class="screen-head"><span class="screen-no">02</span><h2>Product Listing (PLP)</h2><span class="ref">FRD-3.x · Catalog, Search &amp; Filters</span></div>
    <div class="frame">
      <div class="browser-bar"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="url">https://www.shopsphere.in/c/electronics</span></div>
      <div class="canvas">
        <div class="topnav"><span class="logo">Shop<b>Sphere</b></span><span class="search">⌕ &nbsp;"wireless earbuds"</span><div class="navicons"><span class="box"></span><span class="box"></span></div></div>
        <div class="lbl" style="margin:12px 0 8px">Home › Electronics › Audio &nbsp;·&nbsp; 1,248 results <span class="anno">3</span></div>
        <div class="row">
          <div style="width:200px">
            <div class="card">
              <div class="lbl" style="margin-bottom:8px">Filters <span class="anno">1</span></div>
              <div class="txtline xs"></div><div class="pill" style="margin:3px 0">Brand ▾</div>
              <div class="pill" style="margin:3px 0">Price ₹ ▾</div>
              <div class="pill" style="margin:3px 0">Rating ▾</div>
              <div class="pill" style="margin:3px 0">Discount ▾</div>
              <div class="pill" style="margin:3px 0">Delivery ▾</div>
            </div>
          </div>
          <div class="col">
            <div class="row" style="justify-content:space-between;margin-bottom:10px">
              <span class="lbl">Showing 1–12</span><span class="pill">Sort: Relevance ▾ <span class="anno">2</span></span>
            </div>
            <div class="grid3">
              <div class="card"><div class="ph" style="height:80px">Product</div><div class="txtline m"></div><div class="txtline s"></div><div class="price">₹ —</div><div class="star">★★★★☆ (1.2k)</div><div class="btn" style="width:100%;margin-top:8px">Add to Cart <span class="anno">4</span></div></div>
              <div class="card"><div class="ph" style="height:80px">Product</div><div class="txtline m"></div><div class="txtline s"></div><div class="price">₹ —</div><div class="star">★★★★★ (840)</div><div class="btn" style="width:100%;margin-top:8px">Add to Cart</div></div>
              <div class="card"><div class="ph" style="height:80px">Product</div><div class="txtline m"></div><div class="txtline s"></div><div class="price">₹ —</div><div class="star">★★★☆☆ (210)</div><div class="btn" style="width:100%;margin-top:8px">Add to Cart</div></div>
              <div class="card"><div class="ph" style="height:80px">Product</div><div class="txtline m"></div><div class="txtline s"></div><div class="price">₹ —</div><div class="star">★★★★☆</div><div class="btn" style="width:100%;margin-top:8px">Add to Cart</div></div>
              <div class="card"><div class="ph" style="height:80px">Product</div><div class="txtline m"></div><div class="txtline s"></div><div class="price">₹ —</div><div class="star">★★★★☆</div><div class="btn" style="width:100%;margin-top:8px">Add to Cart</div></div>
              <div class="card"><div class="ph" style="height:80px">Product</div><div class="txtline m"></div><div class="txtline s"></div><div class="price">₹ —</div><div class="star">★★★★★</div><div class="btn" style="width:100%;margin-top:8px">Add to Cart</div></div>
            </div>
            <div style="text-align:center;margin-top:14px"><span class="pill">‹ 1 2 3 … 24 › <span class="anno">5</span></span></div>
          </div>
        </div>
        <div style="height:14px"></div>
      </div>
    </div>
    <div class="notes">
      <h4>Annotations</h4>
      <ul>
        <li><span class="n">1</span><div>Faceted filters; multi-select, URL-persisted state — <code>FRD-3.3</code></div></li>
        <li><span class="n">2</span><div>Sort: relevance, price, rating, newest, discount — <code>FRD-3.4</code></div></li>
        <li><span class="n">3</span><div>Breadcrumb + result count; SEO-friendly URLs — <code>FRD-3.1</code></div></li>
        <li><span class="n">4</span><div>Quick add-to-cart without leaving the page — <code>FRD-4.1</code></div></li>
        <li><span class="n">5</span><div>Pagination / infinite scroll (config) — <code>FRD-3.5</code></div></li>
      </ul>
    </div>
  </section>

  <!-- 03 PDP -->
  <section class="screen" id="s3">
    <div class="screen-head"><span class="screen-no">03</span><h2>Product Detail (PDP)</h2><span class="ref">FRD-3.6 / 4.x · Product &amp; Add-to-Cart</span></div>
    <div class="frame">
      <div class="browser-bar"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="url">https://www.shopsphere.in/p/SKU-88421</span></div>
      <div class="canvas">
        <div class="row">
          <div style="width:90px">
            <div class="ph" style="height:50px;margin-bottom:6px">img</div><div class="ph" style="height:50px;margin-bottom:6px">img</div>
            <div class="ph" style="height:50px;margin-bottom:6px">img</div><div class="ph" style="height:50px">img</div>
          </div>
          <div class="ph" style="flex:1.4;min-height:240px">Main Product Image / Zoom <span class="anno">1</span></div>
          <div class="col" style="flex:1.6">
            <div class="txtline m" style="height:14px"></div>
            <div class="star" style="margin:6px 0">★★★★☆ 4.3 · 2,140 ratings · 312 reviews</div>
            <div class="price" style="font-size:22px">₹ — &nbsp;<span style="font-size:12px;color:#8a97a4;font-weight:400">(28% off)</span><span class="anno">2</span></div>
            <div class="lbl" style="margin:12px 0 6px">Variant — Colour / Size <span class="anno">3</span></div>
            <div class="row"><span class="pill">Black</span><span class="pill">White</span><span class="pill">Blue</span></div>
            <div class="row" style="margin-top:12px;align-items:center">
              <span class="search" style="max-width:170px">⌕ Enter pincode — check delivery<span class="anno">4</span></span>
            </div>
            <div class="row" style="margin-top:14px">
              <span class="btn" style="flex:1">Add to Cart</span><span class="btn fill" style="flex:1">Buy Now <span class="anno">5</span></span>
            </div>
            <div class="lbl" style="margin-top:14px">✓ Easy 7-day returns · ✓ COD available · ✓ Secure payment</div>
          </div>
        </div>
        <div class="row" style="margin-top:18px">
          <div class="col"><div class="lbl" style="margin-bottom:6px">Description · Specs · Q&amp;A <span class="anno">6</span></div>
            <div class="txtline"></div><div class="txtline m"></div><div class="txtline s"></div></div>
          <div class="col"><div class="lbl" style="margin-bottom:6px">Ratings &amp; Reviews <span class="anno">7</span></div>
            <div class="card"><div class="star">★★★★★</div><div class="txtline m"></div><div class="txtline s"></div></div></div>
        </div>
        <div class="lbl" style="margin:16px 0 8px">Similar / Frequently Bought Together</div>
        <div class="grid4"><div class="ph" style="height:60px">Product</div><div class="ph" style="height:60px">Product</div><div class="ph" style="height:60px">Product</div><div class="ph" style="height:60px">Product</div></div>
        <div style="height:8px"></div>
      </div>
    </div>
    <div class="notes">
      <h4>Annotations</h4>
      <ul>
        <li><span class="n">1</span><div>Image gallery + zoom; supports video — <code>FRD-3.6</code></div></li>
        <li><span class="n">2</span><div>Price, MRP strike-through, discount badge — <code>FRD-3.7</code></div></li>
        <li><span class="n">3</span><div>Variant selection drives SKU &amp; stock — <code>FRD-3.8</code></div></li>
        <li><span class="n">4</span><div>Pincode → serviceability &amp; ETA (logistics API) — <code>FRD-6.3</code></div></li>
        <li><span class="n">5</span><div>Add-to-cart &amp; express Buy-Now path — <code>FRD-4.1 / 5.1</code></div></li>
        <li><span class="n">6</span><div>Structured specs &amp; customer Q&amp;A — <code>FRD-3.9</code></div></li>
        <li><span class="n">7</span><div>Verified-purchase reviews, helpfulness — <code>FRD-9.1</code></div></li>
      </ul>
    </div>
  </section>

  <!-- 04 CART -->
  <section class="screen" id="s4">
    <div class="screen-head"><span class="screen-no">04</span><h2>Shopping Cart</h2><span class="ref">FRD-4.x · Cart &amp; Pricing</span></div>
    <div class="frame">
      <div class="browser-bar"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="url">https://www.shopsphere.in/cart</span></div>
      <div class="canvas">
        <div class="row">
          <div class="col" style="flex:1.8">
            <div class="lbl" style="margin-bottom:8px">My Cart (3 items) <span class="anno">1</span></div>
            <div class="card row" style="align-items:center;margin-bottom:10px"><div class="ph" style="width:64px;height:54px">img</div><div class="col"><div class="txtline m"></div><div class="txtline xs"></div><span class="lbl">Qty: <span class="pill" style="padding:2px 8px">– 1 +</span> <span class="anno">2</span></span></div><div class="price">₹ —</div></div>
            <div class="card row" style="align-items:center;margin-bottom:10px"><div class="ph" style="width:64px;height:54px">img</div><div class="col"><div class="txtline m"></div><div class="txtline xs"></div><span class="lbl">Qty: <span class="pill" style="padding:2px 8px">– 2 +</span></span></div><div class="price">₹ —</div></div>
            <div class="card row" style="align-items:center"><div class="ph" style="width:64px;height:54px">img</div><div class="col"><div class="txtline m"></div><div class="txtline xs"></div><span class="lbl">Save for later · Remove <span class="anno">3</span></span></div><div class="price">₹ —</div></div>
          </div>
          <div class="col">
            <div class="card">
              <div class="lbl" style="margin-bottom:8px">Order Summary <span class="anno">4</span></div>
              <div class="row" style="justify-content:space-between"><span class="lbl">Subtotal</span><span class="lbl">₹ —</span></div>
              <div class="row" style="justify-content:space-between"><span class="lbl">Delivery</span><span class="lbl">₹ —</span></div>
              <div class="row" style="justify-content:space-between"><span class="lbl">GST</span><span class="lbl">₹ —</span></div>
              <div class="search" style="margin:10px 0">⌕ Apply coupon code <span class="anno">5</span></div>
              <div class="row" style="justify-content:space-between"><span style="font-weight:700">Total</span><span style="font-weight:700">₹ —</span></div>
              <div class="btn fill" style="width:100%;margin-top:12px">Proceed to Checkout <span class="anno">6</span></div>
            </div>
          </div>
        </div>
        <div style="height:8px"></div>
      </div>
    </div>
    <div class="notes">
      <h4>Annotations</h4>
      <ul>
        <li><span class="n">1</span><div>Persistent cart across devices for logged-in users — <code>FRD-4.2</code></div></li>
        <li><span class="n">2</span><div>Quantity update revalidates stock &amp; price — <code>FRD-4.3</code></div></li>
        <li><span class="n">3</span><div>Save-for-later &amp; wishlist move — <code>FRD-4.4</code></div></li>
        <li><span class="n">4</span><div>Live price breakup incl. GST &amp; delivery — <code>FRD-4.5</code></div></li>
        <li><span class="n">5</span><div>Coupon / promo engine validation — <code>FRD-4.6</code></div></li>
        <li><span class="n">6</span><div>Guest or login-gated checkout entry — <code>FRD-5.1</code></div></li>
      </ul>
    </div>
  </section>

  <!-- 05 CHECKOUT -->
  <section class="screen" id="s5">
    <div class="screen-head"><span class="screen-no">05</span><h2>Checkout (Multi-step)</h2><span class="ref">FRD-5.x · Checkout &amp; Payment</span></div>
    <div class="frame">
      <div class="browser-bar"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="url">https://www.shopsphere.in/checkout</span></div>
      <div class="canvas">
        <div class="row" style="justify-content:center;gap:8px;margin-bottom:14px">
          <span class="pill" style="background:var(--accent);color:#fff;border-color:var(--accent)">1 · Address</span>
          <span class="lbl">———</span><span class="pill">2 · Delivery</span>
          <span class="lbl">———</span><span class="pill">3 · Payment</span>
          <span class="lbl">———</span><span class="pill">4 · Review</span>
        </div>
        <div class="row">
          <div class="col" style="flex:1.8">
            <div class="card" style="margin-bottom:12px">
              <div class="lbl" style="margin-bottom:8px">1 · Delivery Address <span class="anno">1</span></div>
              <div class="grid2"><div class="box" style="height:30px"></div><div class="box" style="height:30px"></div></div>
              <div class="box" style="height:30px;margin-top:8px"></div>
              <div class="grid3" style="margin-top:8px"><div class="box" style="height:30px"></div><div class="box" style="height:30px"></div><div class="box" style="height:30px"></div></div>
              <span class="lbl" style="display:block;margin-top:8px">📍 Saved addresses · Add new</span>
            </div>
            <div class="card" style="margin-bottom:12px">
              <div class="lbl" style="margin-bottom:8px">2 · Delivery Options <span class="anno">2</span></div>
              <div class="row"><span class="pill">Standard · Free</span><span class="pill">Express · ₹—</span><span class="pill">Slot delivery</span></div>
            </div>
            <div class="card">
              <div class="lbl" style="margin-bottom:8px">3 · Payment Method <span class="anno">3</span></div>
              <div class="row" style="flex-wrap:wrap;gap:8px"><span class="pill">UPI</span><span class="pill">Cards</span><span class="pill">Net Banking</span><span class="pill">Wallets</span><span class="pill">EMI</span><span class="pill">COD <span class="anno">4</span></span></div>
            </div>
          </div>
          <div class="col">
            <div class="card">
              <div class="lbl" style="margin-bottom:8px">Order Review <span class="anno">5</span></div>
              <div class="txtline"></div><div class="txtline m"></div>
              <div class="row" style="justify-content:space-between;margin-top:8px"><span style="font-weight:700">Total payable</span><span style="font-weight:700">₹ —</span></div>
              <div class="btn fill" style="width:100%;margin-top:12px">Place Order <span class="anno">6</span></div>
              <div class="lbl" style="margin-top:10px;text-align:center">🔒 PCI-DSS secured · 3-D Secure</div>
            </div>
          </div>
        </div>
        <div style="height:6px"></div>
      </div>
    </div>
    <div class="notes">
      <h4>Annotations</h4>
      <ul>
        <li><span class="n">1</span><div>Address w/ pincode autofill &amp; GST invoice option — <code>FRD-5.2</code></div></li>
        <li><span class="n">2</span><div>Delivery options &amp; slots from logistics engine — <code>FRD-6.3</code></div></li>
        <li><span class="n">3</span><div>PCI-DSS payment gateway; UPI/cards/EMI — <code>FRD-5.3</code></div></li>
        <li><span class="n">4</span><div>Cash-on-Delivery with risk checks — <code>FRD-5.4</code></div></li>
        <li><span class="n">5</span><div>Final review before commit; edit any step — <code>FRD-5.5</code></div></li>
        <li><span class="n">6</span><div>Idempotent order placement, failure recovery — <code>FRD-5.6 / SRS-NFR-Reliability</code></div></li>
      </ul>
    </div>
  </section>

  <!-- 06 ACCOUNT -->
  <section class="screen" id="s6">
    <div class="screen-head"><span class="screen-no">06</span><h2>Account &amp; Order Tracking</h2><span class="ref">FRD-7.x / 8.x · Account &amp; Orders</span></div>
    <div class="frame">
      <div class="browser-bar"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="url">https://www.shopsphere.in/account/orders</span></div>
      <div class="canvas">
        <div class="row">
          <div style="width:190px">
            <div class="card"><div class="lbl" style="margin-bottom:8px">My Account <span class="anno">1</span></div>
              <div class="txtline xs"></div><div class="pill" style="margin:3px 0">Orders</div><div class="pill" style="margin:3px 0">Addresses</div>
              <div class="pill" style="margin:3px 0">Wishlist</div><div class="pill" style="margin:3px 0">Wallet / Refunds</div><div class="pill" style="margin:3px 0">Settings</div></div>
          </div>
          <div class="col">
            <div class="lbl" style="margin-bottom:8px">Order History</div>
            <div class="card" style="margin-bottom:10px">
              <div class="row" style="justify-content:space-between"><span class="lbl">Order #SHS-2026-00188</span><span class="pill" style="color:var(--ok);border-color:var(--ok)">Delivered</span></div>
              <div class="row" style="margin-top:10px;align-items:center"><div class="ph" style="width:54px;height:46px">img</div><div class="col"><div class="txtline m"></div><div class="txtline xs"></div></div><span class="btn">Reorder</span><span class="btn">Return <span class="anno">3</span></span></div>
            </div>
            <div class="card">
              <div class="row" style="justify-content:space-between"><span class="lbl">Order #SHS-2026-00211</span><span class="pill" style="color:var(--note);border-color:var(--note)">Out for delivery</span></div>
              <div class="lbl" style="margin:10px 0 6px">Tracking <span class="anno">2</span></div>
              <div class="row" style="align-items:center;gap:4px"><span class="pill" style="background:var(--ok);color:#fff;border-color:var(--ok)">Placed</span>——<span class="pill" style="background:var(--ok);color:#fff;border-color:var(--ok)">Packed</span>——<span class="pill" style="background:var(--ok);color:#fff;border-color:var(--ok)">Shipped</span>——<span class="pill" style="background:var(--note);color:#fff;border-color:var(--note)">Out</span>——<span class="pill">Delivered</span></div>
            </div>
          </div>
        </div>
        <div style="height:8px"></div>
      </div>
    </div>
    <div class="notes">
      <h4>Annotations</h4>
      <ul>
        <li><span class="n">1</span><div>Self-service profile, addresses, wallet &amp; refunds — <code>FRD-7.1</code></div></li>
        <li><span class="n">2</span><div>Real-time order tracking via logistics webhooks — <code>FRD-8.2</code></div></li>
        <li><span class="n">3</span><div>Returns / refunds workflow &amp; status — <code>FRD-8.3</code></div></li>
      </ul>
    </div>
  </section>

  <!-- 07 ADMIN -->
  <section class="screen" id="s7">
    <div class="screen-head"><span class="screen-no">07</span><h2>Admin &amp; Supply-Chain Console</h2><span class="ref">FRD-10.x / 6.x · Operations</span></div>
    <div class="frame">
      <div class="browser-bar"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="url">https://admin.shopsphere.in/dashboard</span></div>
      <div class="canvas">
        <div class="row">
          <div style="width:160px">
            <div class="card" style="background:#eef2f6"><div class="logo" style="font-size:13px;margin-bottom:10px">Shop<b>Sphere</b> Ops</div>
              <div class="pill" style="margin:3px 0;display:block">Dashboard</div><div class="pill" style="margin:3px 0;display:block">Catalog</div>
              <div class="pill" style="margin:3px 0;display:block">Orders</div><div class="pill" style="margin:3px 0;display:block">Inventory</div>
              <div class="pill" style="margin:3px 0;display:block">Logistics</div><div class="pill" style="margin:3px 0;display:block">Promotions</div>
              <div class="pill" style="margin:3px 0;display:block">Reports</div></div>
          </div>
          <div class="col">
            <div class="grid4" style="margin-bottom:12px">
              <div class="card"><div class="lbl">GMV today</div><div class="price" style="font-size:18px">₹ —</div><span class="anno">1</span></div>
              <div class="card"><div class="lbl">Orders</div><div class="price" style="font-size:18px">—</div></div>
              <div class="card"><div class="lbl">Conversion</div><div class="price" style="font-size:18px">—%</div></div>
              <div class="card"><div class="lbl">Low-stock SKUs</div><div class="price" style="font-size:18px;color:var(--note)">—</div><span class="anno">2</span></div>
            </div>
            <div class="row">
              <div class="col"><div class="lbl" style="margin-bottom:6px">Sales Trend <span class="anno">3</span></div><div class="ph" style="height:110px">Chart</div></div>
              <div class="col"><div class="lbl" style="margin-bottom:6px">Inventory &amp; Fulfilment <span class="anno">4</span></div>
                <div class="card"><div class="row" style="justify-content:space-between"><span class="lbl">Warehouse A</span><span class="lbl">82%</span></div><div class="txtline m"></div>
                <div class="row" style="justify-content:space-between;margin-top:6px"><span class="lbl">Warehouse B</span><span class="lbl">— %</span></div><div class="txtline s"></div></div>
              </div>
            </div>
            <div class="lbl" style="margin:12px 0 6px">Order Queue · pick / pack / ship <span class="anno">5</span></div>
            <div class="box" style="height:48px"></div>
          </div>
        </div>
        <div style="height:6px"></div>
      </div>
    </div>
    <div class="notes">
      <h4>Annotations</h4>
      <ul>
        <li><span class="n">1</span><div>Real-time KPI tiles (GMV, orders, AOV) — <code>FRD-10.1</code></div></li>
        <li><span class="n">2</span><div>Low-stock &amp; reorder alerts from inventory engine — <code>FRD-6.1</code></div></li>
        <li><span class="n">3</span><div>Analytics dashboards &amp; exportable reports — <code>FRD-10.2</code></div></li>
        <li><span class="n">4</span><div>Multi-warehouse stock view, ERP/WMS sync — <code>FRD-6.2</code></div></li>
        <li><span class="n">5</span><div>Fulfilment workflow &amp; courier allocation — <code>FRD-6.4</code></div></li>
      </ul>
    </div>
  </section>

  <!-- 08 MOBILE -->
  <section class="screen" id="s8">
    <div class="screen-head"><span class="screen-no">08</span><h2>Mobile App (iOS / Android)</h2><span class="ref">SRS-NFR · Responsive &amp; Native Parity</span></div>
    <div class="phones">
      <div class="phone"><div class="notch"></div><div class="pscreen">
        <div class="search" style="margin-bottom:10px">⌕ Search</div>
        <div class="ph" style="height:70px;margin-bottom:10px">Banner</div>
        <div class="grid2"><div class="ph" style="height:44px">Cat</div><div class="ph" style="height:44px">Cat</div><div class="ph" style="height:44px">Cat</div><div class="ph" style="height:44px">Cat</div></div>
        <div class="lbl" style="margin:10px 0 6px">For you</div>
        <div class="grid2"><div class="card" style="padding:6px"><div class="ph" style="height:50px">P</div><div class="price">₹—</div></div><div class="card" style="padding:6px"><div class="ph" style="height:50px">P</div><div class="price">₹—</div></div></div>
        <div class="tabbar"><span class="box"></span><span class="box"></span><span class="box"></span><span class="box"></span></div>
      </div><div class="cap">Home</div></div>

      <div class="phone"><div class="notch"></div><div class="pscreen">
        <div class="ph" style="height:140px;margin-bottom:10px">Product Image</div>
        <div class="txtline m"></div><div class="star" style="margin:6px 0">★★★★☆ 4.3</div>
        <div class="price" style="font-size:18px">₹ —</div>
        <div class="row" style="margin-top:8px"><span class="pill">Black</span><span class="pill">Blue</span></div>
        <div class="search" style="margin:10px 0">⌕ Pincode — delivery ETA</div>
        <div class="row"><span class="btn" style="flex:1">Cart</span><span class="btn fill" style="flex:1">Buy</span></div>
        <div class="tabbar"><span class="box"></span><span class="box"></span><span class="box"></span><span class="box"></span></div>
      </div><div class="cap">Product</div></div>

      <div class="phone"><div class="notch"></div><div class="pscreen">
        <div class="lbl" style="margin-bottom:8px">Cart · 2 items</div>
        <div class="card row" style="padding:6px;margin-bottom:8px;align-items:center"><div class="ph" style="width:40px;height:36px">i</div><div class="col"><div class="txtline xs"></div><div class="price">₹—</div></div></div>
        <div class="card row" style="padding:6px;margin-bottom:10px;align-items:center"><div class="ph" style="width:40px;height:36px">i</div><div class="col"><div class="txtline xs"></div><div class="price">₹—</div></div></div>
        <div class="search" style="margin-bottom:8px">⌕ Coupon</div>
        <div class="row" style="justify-content:space-between"><span style="font-weight:700">Total</span><span style="font-weight:700">₹—</span></div>
        <div class="btn fill" style="width:100%;margin-top:10px">Checkout</div>
        <div class="lbl" style="text-align:center;margin-top:8px">🔒 UPI · Cards · COD</div>
        <div class="tabbar"><span class="box"></span><span class="box"></span><span class="box"></span><span class="box"></span></div>
      </div><div class="cap">Cart &amp; Checkout</div></div>
    </div>
    <div class="notes" style="margin-top:18px">
      <h4>Notes</h4>
      <ul>
        <li><span class="n">i</span><div>Feature parity with web; native UPI &amp; push notifications — <code>SRS-NFR-Usability</code></div></li>
        <li><span class="n">i</span><div>Optimised for low-bandwidth networks &amp; mid-range devices — <code>SRS-NFR-Performance</code></div></li>
      </ul>
    </div>
  </section>

  <div class="footnote">
    <span>ShopSphere · Project Horizon · Wireframe Set v1.0 — low-fidelity, for requirements validation only.</span>
    <span>Meridian Retail Pvt. Ltd. · Confidential</span>
  </div>
</div>
</body>
</html>
