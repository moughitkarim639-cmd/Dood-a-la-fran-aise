<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Food à la Française – Menu</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=Lato:wght@300;400;700&display=swap" rel="stylesheet">
<style>
:root {
  --pink: #e0157a;
  --red: #c0392b;
  --gold: #e8b84b;
  --dark: #0f0f0f;
  --card: #1a1a1a;
  --card2: #202020;
  --border: #2e2e2e;
  --text: #e8e0d5;
  --muted: #888;
  --green: #27ae60;
}
* { margin: 0; padding: 0; box-sizing: border-box; }
body { background: var(--dark); color: var(--text); font-family: 'Lato', sans-serif; min-height: 100vh; }

/* ── STICKY NAV ── */
.sticky-nav {
  position: sticky; top: 0; z-index: 100;
  background: #0a0a0aee;
  backdrop-filter: blur(8px);
  border-bottom: 1px solid var(--border);
  display: flex; align-items: center; justify-content: space-between;
  padding: 10px 20px; gap: 12px;
}
.nav-logo {
  font-family: 'Playfair Display', serif;
  font-style: italic;
  font-size: 1.4rem;
  color: var(--pink);
  letter-spacing: 1px;
  white-space: nowrap;
}
.nav-logo span { color: #fff; font-style: normal; }
.nav-tabs { display: flex; gap: 6px; flex-wrap: wrap; }
.nav-tab {
  background: transparent;
  border: 1px solid var(--border);
  color: var(--muted);
  padding: 5px 12px;
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 1px;
  cursor: pointer;
  transition: all 0.2s;
  text-transform: uppercase;
}
.nav-tab:hover, .nav-tab.active { background: var(--pink); border-color: var(--pink); color: #fff; }
.cart-btn {
  background: var(--pink);
  border: none;
  color: #fff;
  padding: 8px 16px;
  border-radius: 22px;
  font-size: 0.85rem;
  font-weight: 700;
  cursor: pointer;
  display: flex; align-items: center; gap: 7px;
  transition: background 0.2s;
  white-space: nowrap;
  flex-shrink: 0;
}
.cart-btn:hover { background: #c01268; }
.cart-count {
  background: #fff;
  color: var(--pink);
  border-radius: 50%;
  width: 20px; height: 20px;
  display: flex; align-items: center; justify-content: center;
  font-size: 0.72rem;
  font-weight: 900;
}

/* ── HEADER ── */
header {
  background: #0a0a0a;
  border-bottom: 2px solid var(--pink);
  padding: 32px 20px 24px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
header::before {
  content: '';
  position: absolute; inset: 0;
  background: radial-gradient(ellipse at center top, rgba(224,21,122,0.12) 0%, transparent 65%);
  pointer-events: none;
}
.brand {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.8rem, 8vw, 5rem);
  font-weight: 900;
  line-height: 1;
  letter-spacing: 2px;
}
.brand-f { color: var(--pink); font-style: italic; }
.brand-ood { color: #fff; }
.brand-sub {
  font-family: 'Playfair Display', serif;
  font-style: italic;
  font-size: clamp(1rem, 3vw, 1.5rem);
  color: var(--gold);
  letter-spacing: 3px;
  margin-top: 4px;
}

/* ── BANNERS ── */
.phone-banner {
  background: var(--red);
  text-align: center; padding: 10px 20px;
  font-size: 1rem; font-weight: 700; letter-spacing: 2px; color: #fff;
  display: flex; align-items: center; justify-content: center; gap: 10px;
}
.phone-banner a { color: #fff; text-decoration: none; }
.phone-banner a:hover { text-decoration: underline; }
.delivery-banner {
  background: #1a3a1a;
  border-bottom: 1px solid #2d6a2d;
  text-align: center; padding: 9px 20px;
  font-size: 0.88rem; font-weight: 700;
  color: #6fcf6f; letter-spacing: 2px;
  display: flex; align-items: center; justify-content: center; gap: 8px;
}

/* ── MAIN ── */
main { max-width: 1100px; margin: 0 auto; padding: 40px 16px 100px; }

/* ── SECTIONS ── */
.menu-section { display: none; }
.menu-section.active { display: block; }

.section-title {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem; font-weight: 900;
  text-transform: uppercase; letter-spacing: 4px;
  text-align: center; color: var(--gold);
  margin-bottom: 28px; position: relative; padding-bottom: 12px;
}
.section-title::after {
  content: ''; position: absolute;
  bottom: 0; left: 50%; transform: translateX(-50%);
  width: 80px; height: 2px; background: var(--pink);
}

/* ── COLUMNS ── */
.columns { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
@media(max-width: 720px) { .columns { grid-template-columns: 1fr; } }
.column-block { display: flex; flex-direction: column; gap: 10px; }

/* ── ITEM CARD ── */
.item-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 14px 16px;
  display: flex; align-items: flex-start;
  justify-content: space-between; gap: 12px;
  transition: border-color 0.2s, transform 0.2s;
  animation: fadeUp 0.4s ease both;
}
.item-card:hover { border-color: var(--pink); transform: translateY(-2px); }
.item-info { flex: 1; }
.item-name {
  font-family: 'Playfair Display', serif;
  font-size: 1rem; font-weight: 700; color: #fff;
  text-transform: uppercase; letter-spacing: 1px; margin-bottom: 3px;
}
.item-desc { font-size: 0.75rem; color: var(--muted); line-height: 1.4; }
.item-right { display: flex; flex-direction: column; align-items: flex-end; gap: 6px; flex-shrink: 0; }
.item-price {
  font-family: 'Playfair Display', serif;
  font-size: 1.05rem; font-weight: 700; color: var(--gold);
  white-space: nowrap;
  background: rgba(232,184,75,0.08);
  border: 1px solid rgba(232,184,75,0.2);
  border-radius: 6px; padding: 4px 10px;
}
.add-btn {
  background: var(--pink); border: none; color: #fff;
  width: 28px; height: 28px; border-radius: 50%;
  font-size: 1.2rem; cursor: pointer; display: flex;
  align-items: center; justify-content: center;
  transition: background 0.2s, transform 0.15s;
  flex-shrink: 0;
}
.add-btn:hover { background: #c01268; transform: scale(1.15); }

/* ── DIVIDER ── */
.divider { height: 1px; background: var(--border); margin: 36px 0; }

/* ── TACOS TABLE ── */
.tacos-table-wrap { overflow-x: auto; }
.tacos-table { width: 100%; border-collapse: collapse; font-size: 0.85rem; }
.tacos-table thead tr { background: var(--red); color: #fff; text-transform: uppercase; letter-spacing: 2px; font-size: 0.75rem; }
.tacos-table thead th { padding: 10px 14px; text-align: left; }
.tacos-table thead th:nth-child(2),
.tacos-table thead th:nth-child(3),
.tacos-table thead th:nth-child(4) { text-align: right; }
.tacos-table tbody tr { border-bottom: 1px solid var(--border); transition: background 0.15s; }
.tacos-table tbody tr:hover { background: rgba(255,255,255,0.04); }
.tacos-table tbody td { padding: 10px 14px; color: var(--text); }
.tacos-table tbody td:nth-child(2),
.tacos-table tbody td:nth-child(3) { text-align: right; color: var(--gold); font-weight: 700; font-family: 'Playfair Display', serif; }
.tacos-table tbody td:nth-child(4) { text-align: right; }
.tacos-table .row-xl { background: rgba(232,184,75,0.08); font-weight: 700; }
.tacos-table .row-xl td:first-child { color: var(--gold); font-size: 1rem; }
.tacos-note { font-size: 0.72rem; color: var(--muted); margin-bottom: 12px; padding-left: 4px; }

/* ── SUPPLEMENTS ── */
.supplements { background: var(--card); border: 1px solid var(--border); border-radius: 10px; padding: 20px; margin-top: 36px; }
.supp-title { font-family: 'Playfair Display', serif; font-size: 1rem; font-weight: 700; text-transform: uppercase; letter-spacing: 3px; color: var(--gold); margin-bottom: 14px; }
.supp-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(160px, 1fr)); gap: 8px; }
.supp-item { display: flex; justify-content: space-between; font-size: 0.82rem; color: var(--text); padding: 6px 0; border-bottom: 1px dotted var(--border); }
.supp-price { color: var(--gold); font-weight: 700; }

/* ── CART OVERLAY ── */
.cart-overlay {
  position: fixed; inset: 0; background: rgba(0,0,0,0.7);
  z-index: 200; display: none; align-items: flex-end; justify-content: center;
}
.cart-overlay.open { display: flex; }
.cart-panel {
  background: #181818;
  border: 1px solid var(--border);
  border-radius: 18px 18px 0 0;
  width: 100%; max-width: 540px;
  max-height: 85vh;
  display: flex; flex-direction: column;
  animation: slideUp 0.3s ease;
}
.cart-header {
  padding: 18px 20px 14px;
  border-bottom: 1px solid var(--border);
  display: flex; align-items: center; justify-content: space-between;
}
.cart-header h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.2rem; color: #fff;
}
.cart-close {
  background: var(--border); border: none; color: var(--text);
  width: 32px; height: 32px; border-radius: 50%; font-size: 1rem;
  cursor: pointer; display: flex; align-items: center; justify-content: center;
}
.cart-close:hover { background: var(--red); color: #fff; }
.cart-body { flex: 1; overflow-y: auto; padding: 16px 20px; }
.cart-empty { text-align: center; color: var(--muted); padding: 40px 0; font-size: 0.9rem; }
.cart-item {
  display: flex; align-items: center; gap: 12px;
  padding: 12px 0; border-bottom: 1px solid var(--border);
}
.cart-item-info { flex: 1; }
.cart-item-name { font-weight: 700; font-size: 0.9rem; color: #fff; }
.cart-item-price { font-size: 0.8rem; color: var(--gold); margin-top: 2px; }
.cart-qty {
  display: flex; align-items: center; gap: 8px;
}
.qty-btn {
  background: var(--card2); border: 1px solid var(--border);
  color: #fff; width: 26px; height: 26px; border-radius: 50%;
  cursor: pointer; font-size: 1rem; display: flex; align-items: center; justify-content: center;
}
.qty-btn:hover { border-color: var(--pink); color: var(--pink); }
.qty-num { font-weight: 700; font-size: 0.9rem; min-width: 18px; text-align: center; }
.cart-footer {
  padding: 16px 20px;
  border-top: 1px solid var(--border);
}
.cart-total {
  display: flex; justify-content: space-between; align-items: center;
  margin-bottom: 14px;
}
.cart-total-label { font-size: 0.9rem; color: var(--muted); }
.cart-total-amount { font-family: 'Playfair Display', serif; font-size: 1.4rem; font-weight: 700; color: var(--gold); }
.order-btn {
  width: 100%; background: var(--pink); border: none; color: #fff;
  padding: 14px; border-radius: 12px; font-size: 1rem; font-weight: 700;
  cursor: pointer; letter-spacing: 1px;
  transition: background 0.2s;
}
.order-btn:hover { background: #c01268; }
.order-btn:disabled { background: #444; cursor: not-allowed; }
.whatsapp-btn {
  width: 100%; background: #25d366; border: none; color: #fff;
  padding: 13px; border-radius: 12px; font-size: 0.95rem; font-weight: 700;
  cursor: pointer; letter-spacing: 1px; margin-top: 8px;
  display: flex; align-items: center; justify-content: center; gap: 8px;
  transition: background 0.2s;
}
.whatsapp-btn:hover { background: #1eb856; }

/* ── TOAST ── */
.toast {
  position: fixed; bottom: 80px; left: 50%; transform: translateX(-50%) translateY(20px);
  background: var(--green); color: #fff;
  padding: 10px 22px; border-radius: 30px;
  font-size: 0.85rem; font-weight: 700;
  opacity: 0; transition: opacity 0.3s, transform 0.3s;
  z-index: 300; pointer-events: none; white-space: nowrap;
}
.toast.show { opacity: 1; transform: translateX(-50%) translateY(0); }

/* ── ANIMATIONS ── */
@keyframes fadeUp { from { opacity: 0; transform: translateY(12px); } to { opacity: 1; transform: translateY(0); } }
@keyframes slideUp { from { transform: translateY(100%); } to { transform: translateY(0); } }

/* ── FOOTER ── */
footer {
  background: #0a0a0a; border-top: 1px solid var(--border);
  text-align: center; padding: 24px;
  color: var(--muted); font-size: 0.8rem; letter-spacing: 1px;
}
footer a { color: var(--gold); text-decoration: none; }
</style>
</head>
<body>

<!-- STICKY NAV -->
<nav class="sticky-nav">
  <div class="nav-logo"><span>f</span><em>ood</em></div>
  <div class="nav-tabs">
    <button class="nav-tab active" onclick="showSection('pizzas', this)">🍕 Pizzas</button>
    <button class="nav-tab" onclick="showSection('tacos', this)">🌯 Tacos</button>
  </div>
  <button class="cart-btn" onclick="toggleCart()">
    🛒 Panier <span class="cart-count" id="cartCount">0</span>
  </button>
</nav>

<!-- HEADER -->
<header>
  <div class="brand">
    <span class="brand-f">f</span><span class="brand-ood">ood</span>
  </div>
  <div class="brand-sub">à la française</div>
</header>

<div class="phone-banner">
  <span>📞</span> Commandez :
  <a href="tel:0522606017">05 22 60 60 17</a>
</div>
<div class="delivery-banner">
  🛵 Livraison disponible sur Casablanca
</div>

<!-- MAIN -->
<main>

  <!-- ══ PIZZAS ══ -->
  <div id="section-pizzas" class="menu-section active">

    <h2 class="section-title">🍅 Sauce Tomate</h2>
    <div class="columns">
      <div class="column-block">
        <div class="item-card"><div class="item-info"><div class="item-name">Margarita</div><div class="item-desc">Mozzarella, olives</div></div><div class="item-right"><div class="item-price">40 dh</div><button class="add-btn" onclick="addToCart('Margarita',40)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Végitarienne</div><div class="item-desc">Mozzarella, champignons, poivrons, tomates fraîches, olives</div></div><div class="item-right"><div class="item-price">45 dh</div><button class="add-btn" onclick="addToCart('Végitarienne',45)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Chicken</div><div class="item-desc">Mozzarella, poulet, poivrons, olives</div></div><div class="item-right"><div class="item-price">50 dh</div><button class="add-btn" onclick="addToCart('Chicken',50)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Regina</div><div class="item-desc">Mozzarella, jambon, champignons</div></div><div class="item-right"><div class="item-price">50 dh</div><button class="add-btn" onclick="addToCart('Regina',50)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Buffalo</div><div class="item-desc">Mozzarella, viande hachée, poivrons, olives</div></div><div class="item-right"><div class="item-price">50 dh</div><button class="add-btn" onclick="addToCart('Buffalo',50)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Mexicane</div><div class="item-desc">Spicy, mozzarella, viande hachée, oignons, olives</div></div><div class="item-right"><div class="item-price">50 dh</div><button class="add-btn" onclick="addToCart('Mexicane',50)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Océane</div><div class="item-desc">Mozzarella, thon, oignons, olives</div></div><div class="item-right"><div class="item-price">50 dh</div><button class="add-btn" onclick="addToCart('Océane',50)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Neptune</div><div class="item-desc">Mozzarella, thon, poivrons, olives</div></div><div class="item-right"><div class="item-price">50 dh</div><button class="add-btn" onclick="addToCart('Neptune',50)">+</button></div></div>
      </div>
      <div class="column-block">
        <div class="item-card"><div class="item-info"><div class="item-name">4 Saisons Américaine</div><div class="item-desc">Mozzarella, jambon, poivrons, olives</div></div><div class="item-right"><div class="item-price">50 dh</div><button class="add-btn" onclick="addToCart('4 Saisons Américaine',50)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">4 Fromages</div><div class="item-desc">Mozzarella, bleu, chèvre, parmesan</div></div><div class="item-right"><div class="item-price">55 dh</div><button class="add-btn" onclick="addToCart('4 Fromages',55)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Casablanca</div><div class="item-desc">Mozzarella, poulet, chèvre, champignons, tomates fraîches</div></div><div class="item-right"><div class="item-price">55 dh</div><button class="add-btn" onclick="addToCart('Casablanca',55)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Spéciale</div><div class="item-desc">Mozzarella, jambon, viande hachée</div></div><div class="item-right"><div class="item-price">55 dh</div><button class="add-btn" onclick="addToCart('Spéciale',55)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Supreme BBQ</div><div class="item-desc">Mozzarella, sauce BBQ, viande hachée, poulet, poivrons</div></div><div class="item-right"><div class="item-price">55 dh</div><button class="add-btn" onclick="addToCart('Supreme BBQ',55)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">L'Américaine</div><div class="item-desc">Mozzarella, pepperoni, poivrons</div></div><div class="item-right"><div class="item-price">55 dh</div><button class="add-btn" onclick="addToCart('L\'Américaine',55)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Texas</div><div class="item-desc">Mozzarella, pepperoni, viande hachée</div></div><div class="item-right"><div class="item-price">55 dh</div><button class="add-btn" onclick="addToCart('Texas',55)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">4 Saisons Marocaine</div><div class="item-desc">Thon, poulet, jambon, viande hachée</div></div><div class="item-right"><div class="item-price">60 dh</div><button class="add-btn" onclick="addToCart('4 Saisons Marocaine',60)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Crevette</div><div class="item-desc">Mozzarella, crevette, olives, poivrons</div></div><div class="item-right"><div class="item-price">60 dh</div><button class="add-btn" onclick="addToCart('Crevette',60)">+</button></div></div>
      </div>
    </div>

    <div class="divider"></div>

    <h2 class="section-title">🥛 Crème Fraîche</h2>
    <div class="columns">
      <div class="column-block">
        <div class="item-card"><div class="item-info"><div class="item-name">Milano</div><div class="item-desc">Mozzarella, jambon, oignons, pommes de terre</div></div><div class="item-right"><div class="item-price">55 dh</div><button class="add-btn" onclick="addToCart('Milano',55)">+</button></div></div>
        <div class="item-card"><div class="item-info"><div class="item-name">Normande</div><div class="item-desc">Mozzarella, poulet, oignons, pommes de terre</div></div><div class="item-right"><div class="item-price">55 dh</div><button class="add-btn" onclick="addToCart('Normande',55)">+</button></div></div>
      </div>
      <div class="column-block">
        <div class="item-card"><div class="item-info"><div class="item-name">Atlantique</div><div class="item-desc">Mozzarella, crevette, olives</div></div><div class="item-right"><div class="item-price">60 dh</div><button class="add-btn" onclick="addToCart('Atlantique',60)">+</button></div></div>
      </div>
    </div>

    <div class="supplements">
      <div class="supp-title">➕ Suppléments</div>
      <div class="supp-grid">
        <div class="supp-item"><span>Mozzarella</span><span class="supp-price">12 dh</span></div>
        <div class="supp-item"><span>Viande</span><span class="supp-price">12 dh</span></div>
        <div class="supp-item"><span>Légumes</span><span class="supp-price">07 dh</span></div>
        <div class="supp-item"><span>Jambon</span><span class="supp-price">12 dh</span></div>
        <div class="supp-item"><span>Thon</span><span class="supp-price">12 dh</span></div>
        <div class="supp-item"><span>Crevette</span><span class="supp-price">15 dh</span></div>
      </div>
    </div>
  </div><!-- /pizzas -->

  <!-- ══ TACOS ══ -->
  <div id="section-tacos" class="menu-section">
    <h2 class="section-title">🌯 Nos Tacos</h2>
    <p class="tacos-note">Menu : Panini + 12 dh &nbsp;|&nbsp; Coca : 10 dh</p>
    <div class="tacos-table-wrap">
      <table class="tacos-table">
        <thead>
          <tr>
            <th>Tacos</th>
            <th>Seul</th>
            <th>Gratiné</th>
            <th></th>
          </tr>
        </thead>
        <tbody>
          <tr><td>Kebab <small style="color:var(--muted)">(Poulet)</small></td><td>27 dh</td><td>37 dh</td><td><button class="add-btn" style="margin-left:auto" onclick="addToCart('Tacos Kebab',27)">+</button></td></tr>
          <tr><td>Poulet <small style="color:var(--muted)">(Poulet)</small></td><td>30 dh</td><td>40 dh</td><td><button class="add-btn" style="margin-left:auto" onclick="addToCart('Tacos Poulet',30)">+</button></td></tr>
          <tr><td>Steak <small style="color:var(--muted)">(Viande hachée)</small></td><td>32 dh</td><td>42 dh</td><td><button class="add-btn" style="margin-left:auto" onclick="addToCart('Tacos Steak',32)">+</button></td></tr>
          <tr><td>Mix <small style="color:var(--muted)">(Steak, Poulet)</small></td><td>34 dh</td><td>44 dh</td><td><button class="add-btn" style="margin-left:auto" onclick="addToCart('Tacos Mix',34)">+</button></td></tr>
          <tr><td>Poisson</td><td>36 dh</td><td>46 dh</td><td><button class="add-btn" style="margin-left:auto" onclick="addToCart('Tacos Poisson',36)">+</button></td></tr>
          <tr><td>Nuggets</td><td>35 dh</td><td>45 dh</td><td><button class="add-btn" style="margin-left:auto" onclick="addToCart('Tacos Nuggets',35)">+</button></td></tr>
          <tr><td>Cordon Bleu</td><td>36 dh</td><td>46 dh</td><td><button class="add-btn" style="margin-left:auto" onclick="addToCart('Tacos Cordon Bleu',36)">+</button></td></tr>
          <tr><td>Spéciale <small style="color:var(--muted)">(Viande hachée, Jambon)</small></td><td>36 dh</td><td>46 dh</td><td><button class="add-btn" style="margin-left:auto" onclick="addToCart('Tacos Spéciale',36)">+</button></td></tr>
          <tr><td>Food <small style="color:var(--muted)">(Viande hachée, Nuggets)</small></td><td>36 dh</td><td>46 dh</td><td><button class="add-btn" style="margin-left:auto" onclick="addToCart('Tacos Food',36)">+</button></td></tr>
          <tr class="row-xl"><td>XL <small style="color:var(--muted)">– 2 Viandes au choix</small></td><td>52 dh</td><td>67 dh</td><td><button class="add-btn" style="margin-left:auto" onclick="addToCart('Tacos XL',52)">+</button></td></tr>
        </tbody>
      </table>
    </div>
  </div><!-- /tacos -->

</main>

<!-- ══ CART OVERLAY ══ -->
<div class="cart-overlay" id="cartOverlay" onclick="closeCartOutside(event)">
  <div class="cart-panel">
    <div class="cart-header">
      <h3>🛒 Mon Panier</h3>
      <button class="cart-close" onclick="toggleCart()">✕</button>
    </div>
    <div class="cart-body" id="cartBody">
      <div class="cart-empty">Votre panier est vide 🍽️</div>
    </div>
    <div class="cart-footer">
      <div class="cart-total">
        <span class="cart-total-label">Total</span>
        <span class="cart-total-amount" id="cartTotal">0 dh</span>
      </div>
      <button class="order-btn" id="orderBtn" onclick="orderByPhone()" disabled>
        📞 Commander par téléphone
      </button>
      <button class="whatsapp-btn" id="whatsappBtn" onclick="orderByWhatsapp()">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.135.561 4.14 1.535 5.874L0 24l6.334-1.512A11.946 11.946 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.818a9.806 9.806 0 01-5.022-1.378l-.36-.214-3.732.891.934-3.618-.235-.372A9.769 9.769 0 012.182 12C2.182 6.57 6.57 2.182 12 2.182c5.43 0 9.818 4.388 9.818 9.818 0 5.43-4.388 9.818-9.818 9.818z"/></svg>
        Commander via WhatsApp
      </button>
    </div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<!-- FOOTER -->
<footer>
  <p>📞 <a href="tel:0522606017">05 22 60 60 17</a> &nbsp;|&nbsp; 🛵 Livraison Casablanca</p>
  <p style="margin-top:8px; font-style:italic; color:#555;">Food à la Française · Pizza · Tacos · Burger · Sandwich</p>
</footer>

<script>
// ── CART STATE ──
let cart = [];

function addToCart(name, price) {
  const existing = cart.find(i => i.name === name);
  if (existing) {
    existing.qty++;
  } else {
    cart.push({ name, price, qty: 1 });
  }
  updateCartUI();
  showToast('✅ ' + name + ' ajouté !');
}

function changeQty(name, delta) {
  const item = cart.find(i => i.name === name);
  if (!item) return;
  item.qty += delta;
  if (item.qty <= 0) cart = cart.filter(i => i.name !== name);
  updateCartUI();
}

function updateCartUI() {
  const total = cart.reduce((s, i) => s + i.price * i.qty, 0);
  const count = cart.reduce((s, i) => s + i.qty, 0);
  document.getElementById('cartCount').textContent = count;
  document.getElementById('cartTotal').textContent = total + ' dh';
  const btn = document.getElementById('orderBtn');
  btn.disabled = cart.length === 0;

  const body = document.getElementById('cartBody');
  if (cart.length === 0) {
    body.innerHTML = '<div class="cart-empty">Votre panier est vide 🍽️</div>';
    return;
  }
  body.innerHTML = cart.map(item => `
    <div class="cart-item">
      <div class="cart-item-info">
        <div class="cart-item-name">${item.name}</div>
        <div class="cart-item-price">${item.price} dh × ${item.qty} = ${item.price * item.qty} dh</div>
      </div>
      <div class="cart-qty">
        <button class="qty-btn" onclick="changeQty('${item.name}',-1)">−</button>
        <span class="qty-num">${item.qty}</span>
        <button class="qty-btn" onclick="changeQty('${item.name}',1)">+</button>
      </div>
    </div>
  `).join('');
}

function toggleCart() {
  document.getElementById('cartOverlay').classList.toggle('open');
}
function closeCartOutside(e) {
  if (e.target === document.getElementById('cartOverlay')) toggleCart();
}

function orderByPhone() {
  window.location.href = 'tel:0522606017';
}

function orderByWhatsapp() {
  if (cart.length === 0) return;
  const lines = cart.map(i => `• ${i.name} ×${i.qty} = ${i.price * i.qty} dh`).join('\n');
  const total = cart.reduce((s, i) => s + i.price * i.qty, 0);
  const msg = encodeURIComponent(`🍕 *Commande – Food à la Française*\n\n${lines}\n\n*Total : ${total} dh*\n\nMerci !`);
  window.open(`https://wa.me/212522606017?text=${msg}`, '_blank');
}

function showToast(msg) {
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  setTimeout(() => t.classList.remove('show'), 2000);
}

// ── NAV TABS ──
function showSection(id, btn) {
  document.querySelectorAll('.menu-section').forEach(s => s.classList.remove('active'));
  document.querySelectorAll('.nav-tab').forEach(b => b.classList.remove('active'));
  document.getElementById('section-' + id).classList.add('active');
  btn.classList.add('active');
}
</script>
</body>
</html>
