<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Fontes de Renda Validadas</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --bg: #0a0a0a;
      --surface: #111111;
      --border: #1e1e1e;
      --gold: #c9a84c;
      --gold-light: #e8c97e;
      --text: #f0ede8;
      --muted: #6b6762;
      --accent: #1a2e1a;
    }

    html { scroll-behavior: smooth; }

    body {
      background-color: var(--bg);
      color: var(--text);
      font-family: 'DM Sans', sans-serif;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 48px 20px 80px;
      position: relative;
      overflow-x: hidden;
    }

    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background:
        radial-gradient(ellipse 60% 50% at 50% 0%, rgba(201,168,76,0.07) 0%, transparent 70%),
        radial-gradient(ellipse 40% 40% at 80% 80%, rgba(26,46,26,0.4) 0%, transparent 60%);
      pointer-events: none;
      z-index: 0;
    }

    .wrapper {
      width: 100%;
      max-width: 480px;
      position: relative;
      z-index: 1;
    }

    .header {
      text-align: center;
      margin-bottom: 48px;
      animation: fadeDown 0.8s ease both;
    }

    .badge {
      display: inline-block;
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--gold);
      border: 1px solid rgba(201,168,76,0.3);
      padding: 6px 16px;
      border-radius: 999px;
      margin-bottom: 24px;
    }

    .header h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(32px, 8vw, 44px);
      font-weight: 900;
      line-height: 1.1;
      color: var(--text);
      margin-bottom: 16px;
    }

    .header h1 span {
      color: var(--gold);
      font-style: italic;
    }

    .header p {
      font-size: 14px;
      font-weight: 300;
      color: var(--muted);
      line-height: 1.7;
      max-width: 340px;
      margin: 0 auto 24px;
    }

    .divider {
      width: 40px;
      height: 1px;
      background: linear-gradient(to right, transparent, var(--gold), transparent);
      margin: 0 auto;
    }

    .section-label {
      font-size: 10px;
      letter-spacing: 4px;
      text-transform: uppercase;
      color: var(--muted);
      text-align: center;
      margin-bottom: 20px;
      animation: fadeDown 0.8s ease 0.2s both;
    }

    .cards {
      display: flex;
      flex-direction: column;
      gap: 14px;
    }

    .card {
      display: flex;
      align-items: center;
      gap: 18px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 20px 22px;
      text-decoration: none;
      color: var(--text);
      position: relative;
      overflow: hidden;
      transition: transform 0.25s ease, border-color 0.25s ease, box-shadow 0.25s ease;
      animation: fadeUp 0.6s ease both;
    }

    .card:nth-child(1) { animation-delay: 0.3s; }
    .card:nth-child(2) { animation-delay: 0.4s; }
    .card:nth-child(3) { animation-delay: 0.5s; }
    .card:nth-child(4) { animation-delay: 0.6s; }
    .card:nth-child(5) { animation-delay: 0.7s; }

    .card::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(201,168,76,0.04), transparent);
      opacity: 0;
      transition: opacity 0.25s ease;
    }

    .card:hover {
      transform: translateY(-2px);
      border-color: rgba(201,168,76,0.4);
      box-shadow: 0 8px 32px rgba(0,0,0,0.4), 0 0 0 1px rgba(201,168,76,0.1);
    }

    .card:hover::before { opacity: 1; }

    .card-icon {
      width: 48px;
      height: 48px;
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 22px;
      flex-shrink: 0;
      background: var(--accent);
      border: 1px solid rgba(201,168,76,0.15);
    }

    .card-body { flex: 1; }

    .card-title {
      font-size: 15px;
      font-weight: 500;
      margin-bottom: 4px;
      color: var(--text);
    }

    .card-desc {
      font-size: 12px;
      color: var(--muted);
      font-weight: 300;
      line-height: 1.5;
    }

    .card-tag {
      font-size: 10px;
      letter-spacing: 1px;
      text-transform: uppercase;
      color: var(--gold);
      background: rgba(201,168,76,0.08);
      border: 1px solid rgba(201,168,76,0.2);
      padding: 4px 10px;
      border-radius: 999px;
      flex-shrink: 0;
    }

    .card-arrow {
      color: var(--muted);
      font-size: 18px;
      flex-shrink: 0;
      transition: transform 0.2s ease, color 0.2s ease;
    }

    .card:hover .card-arrow {
      transform: translateX(3px);
      color: var(--gold);
    }

    .footer {
      margin-top: 56px;
      text-align: center;
      animation: fadeUp 0.6s ease 0.9s both;
    }

    .footer-quote {
      font-family: 'Playfair Display', serif;
      font-style: italic;
      font-size: 16px;
      color: var(--muted);
      margin-bottom: 8px;
    }

    .footer-quote span { color: var(--gold); }

    .footer-sub {
      font-size: 11px;
      color: #333;
      letter-spacing: 2px;
      text-transform: uppercase;
    }

    @keyframes fadeDown {
      from { opacity: 0; transform: translateY(-16px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <div class="wrapper">

    <div class="header">
      <div class="badge">Fontes Validadas</div>
      <h1>Quem vende,<br/><span>prospera.</span></h1>
      <p>Não espero 30 dias pelo meu dinheiro. Crio minhas fontes de renda e aqui mostro como você também pode.</p>
      <div class="divider"></div>
    </div>

    <p class="section-label">Escolha sua fonte de renda</p>

    <div class="cards">

      <!-- TROQUE "SEU_LINK_CAKTO_DOCES" pelo seu link de afiliado da Cakto -->
      <a href="SEU_LINK_CAKTO_DOCES" target="_blank" class="card">
        <div class="card-icon">🍫</div>
        <div class="card-body">
          <div class="card-title">Ganhe com doces</div>
          <div class="card-desc">Receitas validadas pra fazer e vender em casa ou na rua</div>
        </div>
        <span class="card-arrow">→</span>
      </a>

      <!-- TROQUE "SEU_LINK_CAKTO_AFILIADOS" pelo seu link de afiliado da Cakto -->
      <a href="SEU_LINK_CAKTO_AFILIADOS" target="_blank" class="card">
        <div class="card-icon">📱</div>
        <div class="card-body">
          <div class="card-title">Ganhe como afiliado</div>
          <div class="card-desc">Venda produtos digitais sem estoque, sem sair de casa</div>
        </div>
        <span class="card-tag">Popular</span>
        <span class="card-arrow">→</span>
      </a>

      <!-- TROQUE "SEU_LINK_CAKTO_MARMITAS" pelo seu link de afiliado da Cakto -->
      <a href="SEU_LINK_CAKTO_MARMITAS" target="_blank" class="card">
        <div class="card-icon">🍱</div>
        <div class="card-body">
          <div class="card-title">Ganhe com marmitas</div>
          <div class="card-desc">Monte sua clientela pelo WhatsApp e receba antes de entregar</div>
        </div>
        <span class="card-arrow">→</span>
      </a>

      <!-- TROQUE "SEU_LINK_CAKTO_SALGADOS" pelo seu link de afiliado da Cakto -->
      <a href="SEU_LINK_CAKTO_SALGADOS" target="_blank" class="card">
        <div class="card-icon">🥐</div>
        <div class="card-body">
          <div class="card-title">Ganhe com salgados</div>
          <div class="card-desc">Do congelado ao artesanal — o que mais vende no Brasil</div>
        </div>
        <span class="card-arrow">→</span>
      </a>

      <!-- TROQUE "SEU_LINK_CAKTO_SERVICOS" pelo seu link de afiliado da Cakto -->
      <a href="SEU_LINK_CAKTO_SERVICOS" target="_blank" class="card">
        <div class="card-icon">🔧</div>
        <div class="card-body">
          <div class="card-title">Ganhe com serviços</div>
          <div class="card-desc">Habilidades simples que o seu bairro já está pagando</div>
        </div>
        <span class="card-arrow">→</span>
      </a>

    </div>

    <div class="footer">
      <p class="footer-quote">"A renda extra que você precisa<br/><span>já está ao seu alcance."</span></p>
      <p class="footer-sub">fontes validadas · resultados reais</p>
    </div>

  </div>
</body>
</html>
