<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>DLS – Digital Labeling System · Product Story & Early Support</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta
    name="description"
    content="Digital Labeling System (DLS) — the operating system for physical retail. Product story, early support & pre-order access for Consumers, Makers, and Stores."
  />
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    :root {
      --bg: #020617;
      --bg-elevated: #020a1f;
      --border-subtle: rgba(148, 163, 184, 0.35);
      --border-soft: rgba(30, 64, 175, 0.7);
      --fg: #e5e7eb;
      --fg-muted: #9ca3af;
      --accent: #38bdf8;
      --accent-soft: rgba(56, 189, 248, 0.16);
      --accent-strong: #0ea5e9;
      --danger: #f97373;
      --radius-xl: 24px;
      --radius-lg: 18px;
      --shadow-soft: 0 18px 40px rgba(15, 23, 42, 0.8);
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background:
        radial-gradient(circle at top left, rgba(56, 189, 248, 0.12), transparent 55%),
        radial-gradient(circle at bottom right, rgba(59, 130, 246, 0.18), transparent 55%),
        var(--bg);
      color: var(--fg);
      min-height: 100vh;
      padding: 32px 16px 40px;
      display: flex;
      justify-content: center;
    }

    .shell {
      width: 100%;
      max-width: 1180px;
    }

    /* HEADER */

    .page-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
      margin-bottom: 28px;
    }

    .logo-row {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .logo-mark {
      width: 32px;
      height: 32px;
      border-radius: 999px;
      background: radial-gradient(circle at 30% 20%, #e0f2fe, #38bdf8 40%, #0f172a 85%);
      box-shadow:
        0 0 0 1px rgba(15, 23, 42, 0.9),
        0 16px 30px rgba(15, 23, 42, 0.9);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 700;
      font-size: 16px;
      color: #0b1120;
    }

    .logo-text-main {
      font-size: 18px;
      font-weight: 600;
      letter-spacing: 0.04em;
    }

    .logo-text-sub {
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.14em;
      color: var(--fg-muted);
    }

    .header-nav {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      justify-content: flex-end;
    }

    .nav-chip {
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.4);
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.96));
      padding: 6px 12px;
      font-size: 11px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--fg-muted);
      display: flex;
      align-items: center;
      gap: 6px;
      cursor: default;
    }

    .nav-chip span.dot {
      width: 5px;
      height: 5px;
      border-radius: 999px;
      background: var(--accent);
    }

    /* MAIN GRID */

    .page-main {
      display: grid;
      grid-template-columns: minmax(0, 390px) minmax(0, 1.1fr);
      gap: 22px;
      align-items: flex-start;
    }

    .page-main-left,
    .page-main-right {
      border-radius: var(--radius-xl);
      background: radial-gradient(circle at top left, rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.98));
      border: 1px solid rgba(15, 23, 42, 0.9);
      box-shadow: var(--shadow-soft);
      padding: 22px 22px 20px;
      position: relative;
      overflow: hidden;
    }

    .page-main-right {
      background:
        radial-gradient(circle at top right, rgba(56, 189, 248, 0.16), transparent 55%),
        radial-gradient(circle at bottom left, rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.98));
      border-color: rgba(37, 99, 235, 0.7);
      padding: 22px 22px 18px;
      max-height: calc(100vh - 140px);
      overflow-y: auto;
      scrollbar-width: thin;
      scrollbar-color: rgba(148, 163, 184, 0.9) transparent;
    }

    .page-main-right::-webkit-scrollbar {
      width: 7px;
    }
    .page-main-right::-webkit-scrollbar-track {
      background: transparent;
    }
    .page-main-right::-webkit-scrollbar-thumb {
      background: rgba(148, 163, 184, 0.5);
      border-radius: 999px;
    }

    .eyebrow {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--fg-muted);
      margin-bottom: 6px;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.45);
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.96));
      padding: 4px 12px;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.15em;
      color: var(--fg-muted);
      margin-bottom: 10px;
    }

    .badge-dot {
      width: 7px;
      height: 7px;
      border-radius: 999px;
      background: var(--accent);
      box-shadow: 0 0 0 3px rgba(56, 189, 248, 0.2);
    }

    .page-main-left h1 {
      font-size: 26px;
      line-height: 1.15;
      margin-bottom: 6px;
    }

    .page-main-left .subtitle {
      font-size: 14px;
      color: var(--fg-muted);
      margin-bottom: 14px;
    }

    .pill-row {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 18px;
    }

    .pill {
      font-size: 11px;
      padding: 4px 10px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.35);
      color: var(--fg-muted);
      background: rgba(15, 23, 42, 0.9);
    }

    .highlight-box {
      border-radius: 16px;
      border: 1px solid rgba(148, 163, 184, 0.4);
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.96), rgba(15, 23, 42, 0.99));
      padding: 12px 12px 11px;
      font-size: 13px;
      color: var(--fg-muted);
      margin-bottom: 16px;
    }

    .highlight-box strong {
      color: var(--fg);
    }

    .support-section {
      margin-top: 2px;
      margin-bottom: 16px;
    }

    .support-section h2 {
      font-size: 15px;
      margin-bottom: 6px;
    }

    .support-section p {
      font-size: 13px;
      line-height: 1.55;
      color: var(--fg-muted);
      margin-bottom: 8px;
    }

    .support-list {
      font-size: 13px;
      line-height: 1.55;
      color: var(--fg-muted);
      margin: 4px 0 10px 16px;
    }

    .support-list li {
      margin-bottom: 2px;
    }

    .plan-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 10px;
      margin-bottom: 16px;
    }

    .plan-card {
      border-radius: 16px;
      border: 1px solid rgba(148, 163, 184, 0.45);
      background:
        radial-gradient(circle at 0% 0%, rgba(56, 189, 248, 0.08), transparent 55%),
        radial-gradient(circle at 100% 100%, rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.98));
      padding: 10px 12px;
      font-size: 13px;
    }

    .plan-card h3 {
      font-size: 14px;
      margin-bottom: 4px;
    }

    .plan-tag {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.45);
      padding: 2px 8px;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      color: var(--fg-muted);
      margin-bottom: 6px;
    }

    .plan-body p {
      margin-bottom: 4px;
      color: var(--fg-muted);
    }

    .plan-body p strong {
      color: var(--fg);
    }

    .plan-save {
      font-size: 12px;
      color: #bbf7d0;
      margin-bottom: 8px;
    }

    .plan-cta {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-size: 12px;
      font-weight: 500;
      padding: 7px 10px;
      border-radius: 999px;
      border: 1px solid rgba(56, 189, 248, 0.6);
      background: radial-gradient(circle at 0% 0%, rgba(56, 189, 248, 0.18), rgba(15, 23, 42, 0.98));
      color: #e0f2fe;
      text-decoration: none;
      gap: 6px;
      cursor: pointer;
    }

    .plan-cta span.icon {
      font-size: 13px;
    }

    .legal-note {
      margin-top: 8px;
      padding-top: 8px;
      border-top: 1px dashed rgba(148, 163, 184, 0.5);
      font-size: 11px;
      line-height: 1.55;
      color: var(--fg-muted);
    }

    .legal-note ul {
      margin: 4px 0 4px 16px;
    }

    .legal-note li {
      margin-bottom: 2px;
    }

    .legal-note-strong {
      font-size: 11px;
      margin-top: 4px;
      color: var(--fg-muted);
    }

    .legal-note-strong strong {
      color: var(--fg);
    }

    /* RIGHT COLUMN – STORY */

    .story-section {
      padding-bottom: 14px;
      border-bottom: 1px solid rgba(148, 163, 184, 0.24);
      margin-bottom: 12px;
    }

    .story-section:last-child {
      border-bottom: none;
      margin-bottom: 0;
      padding-bottom: 0;
    }

    .story-section h1,
    .story-section h2,
    .story-section h3,
    .story-section h4,
    .story-section h5 {
      margin-bottom: 6px;
    }

    .story-section h1 {
      font-size: 22px;
      line-height: 1.2;
    }

    .story-section h2 {
      font-size: 16px;
      margin-top: 2px;
    }

    .story-section h3 {
      font-size: 14px;
      text-transform: none;
    }

    .story-section h4 {
      font-size: 13px;
      text-transform: none;
    }

    .story-section h5 {
      font-size: 13px;
      font-weight: 500;
    }

    .story-section p {
      font-size: 13px;
      line-height: 1.6;
      color: var(--fg-muted);
      margin-bottom: 6px;
    }

    .story-section ul {
      font-size: 13px;
      line-height: 1.6;
      color: var(--fg-muted);
      margin: 4px 0 8px 18px;
    }

    .story-section ul li {
      margin-bottom: 2px;
    }

    /* FOUNDER */

    .founder-card {
      margin-top: 22px;
      border-radius: var(--radius-xl);
      border: 1px solid rgba(148, 163, 184, 0.4);
      background:
        radial-gradient(circle at 0% 0%, rgba(56, 189, 248, 0.14), transparent 55%),
        radial-gradient(circle at 100% 100%, rgba(15, 23, 42, 0.96), rgba(15, 23, 42, 0.99));
      padding: 18px 18px 16px;
      box-shadow: var(--shadow-soft);
      display: grid;
      grid-template-columns: auto minmax(0, 1fr);
      gap: 14px;
      align-items: flex-start;
    }

    .founder-avatar {
      width: 64px;
      height: 64px;
      border-radius: 999px;
      background: radial-gradient(circle at 30% 20%, #e0f2fe, #38bdf8 40%, #0f172a 90%);
      border: 2px solid rgba(15, 23, 42, 0.95);
      box-shadow:
        0 0 0 3px rgba(15, 23, 42, 0.9),
        0 16px 32px rgba(15, 23, 42, 0.9);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 700;
      font-size: 24px;
      color: #0b1120;
    }

    .founder-main h3 {
      font-size: 15px;
      margin-bottom: 2px;
    }

    .founder-main .role {
      font-size: 12px;
      color: var(--fg-muted);
      margin-bottom: 8px;
    }

    .founder-main p {
      font-size: 13px;
      line-height: 1.6;
      color: var(--fg-muted);
      margin-bottom: 6px;
    }

    .founder-columns {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 10px;
      margin-top: 4px;
    }

    .founder-col h4 {
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      color: var(--fg-muted);
      margin-bottom: 4px;
    }

    .founder-col p {
      font-size: 13px;
      line-height: 1.5;
      margin-bottom: 4px;
    }

    .founder-footer {
      margin-top: 6px;
      font-size: 12px;
      color: var(--fg-muted);
    }

    /* FOOTER */

    .page-footer {
      margin-top: 18px;
      font-size: 11px;
      color: var(--fg-muted);
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 6px;
    }

    /* RESPONSIVE */

    @media (max-width: 960px) {
      .page-main {
        grid-template-columns: minmax(0, 1fr);
      }

      .page-main-right {
        max-height: none;
      }

      .founder-card {
        grid-template-columns: minmax(0, 1fr);
      }

      body {
        padding-top: 20px;
      }

      .page-header {
        flex-direction: column;
        align-items: flex-start;
      }

      .header-nav {
        justify-content: flex-start;
      }
    }
  </style>
</head>
<body>
  <div class="shell">
    <!-- HEADER -->
    <header class="page-header">
      <div class="logo-row">
        <div class="logo-mark">D</div>
        <div>
          <div class="logo-text-main">Digital Labeling System</div>
          <div class="logo-text-sub">DLS · Product Story &amp; Early Support</div>
        </div>
      </div>
      <nav class="header-nav">
        <div class="nav-chip">
          <span class="dot"></span>
          Product Story
        </div>
        <div class="nav-chip">
          <span class="dot"></span>
          Early Support
        </div>
        <div class="nav-chip">
          <span class="dot"></span>
          Founder
        </div>
      </nav>
    </header>

    <!-- MAIN -->
    <main class="page-main">
      <!-- LEFT: EARLY SUPPORT & PLANS -->
      <section class="page-main-left" id="early-support">
        <div class="badge">
          <span class="badge-dot"></span>
          Early Support &amp; Pre-Order Access
        </div>

        <h1>Early Support &amp; Pre-Order Access</h1>
        <p class="subtitle">
          Help launch DLS today and lock in discounted access for tomorrow.
        </p>

        <div class="pill-row">
          <div class="pill">Consumers</div>
          <div class="pill">Makers (1 product)</div>
          <div class="pill">Stores (50–200 products)</div>
        </div>

        <div class="highlight-box">
          <strong>DLS gives each physical product</strong>
          a permanent digital identity, AI-managed pricing, inventory control,
          and ESG / compliance visibility.
        </div>

        <section class="support-section">
          <h2>How the early-support model works</h2>

          <p>
            DLS gives each physical product a permanent digital identity, AI-managed pricing,
            inventory control, and ESG / compliance visibility. Today, we invite three direct user
            groups — Consumers, Makers, and Retail Stores — to support the launch by pre-ordering
            their future subscription through an early-support contribution.
          </p>

          <p>
            How the early-support model works
          </p>

          <p>
            We do not treat your payment as a classic “investment”. There is no promise of equity,
            no profit share, no securities. Instead, your payment is a donation-like early supporter
            contribution that is directly linked to a future subscription to the DLS platform after launch.
          </p>

          <p>
            You pay a small, fixed amount today to help us develop infrastructure, and in return you
            lock in a discounted 2-year subscription once the product goes live. The idea is simple:
            spend a little today so that tomorrow your operations are cheaper and more convenient.
          </p>

          <ul class="support-list">
            <li>Pre-order, not equity</li>
            <li>2 years access after launch</li>
            <li>Same core product, different roles</li>
            <li>Save vs future monthly price</li>
          </ul>

          <p>
            We have three direct end-user roles with their own economics:
          </p>

          <ul class="support-list">
            <li>Consumers — use DLS to scan, verify, and pay for products with their phone.</li>
            <li>Makers (one product) — small manufacturers that want one key product to be fully traceable and smart.</li>
            <li>Stores (50–200 products) — retail locations that want AI pricing, live inventory, and scan-to-pay checkout.</li>
          </ul>

          <p>
            For each group we show:
          </p>

          <ul class="support-list">
            <li>the future monthly subscription price,</li>
            <li>the 2-year value at that price,</li>
            <li>what you actually pay today as an early supporter,</li>
            <li>how much you save by supporting now instead of waiting.</li>
          </ul>

          <p>
            Access is planned to start within 12 months, with 2 full years of use from the official
            launch date. If launch is delayed, your 2-year access shifts accordingly — you always get the full duration.
          </p>

          <p>
            Three direct user plans · one shared platform.
            Choose your role, see your future subscription, and decide if supporting DLS today is worth the savings.
          </p>
        </section>

        <!-- PLANS -->
        <section class="plan-grid">
          <!-- CONSUMER -->
          <article class="plan-card" id="support-consumer">
            <div class="plan-tag">
              <span>Consumer Plan</span>
            </div>
            <h3>Consumer Plan</h3>
            <div class="plan-body">
              <p>
                For individual users who want to scan, verify, and pay for products with their phone,
                and keep digital receipts and history.
              </p>

              <p><strong>Future subscription</strong></p>
              <p>$9.99 / month</p>
              <p>2-year value: 24 × $9.99 ≈ $239.76</p>

              <p><strong>Early supporter contribution</strong></p>
              <p>Pay $100 once today for 2 years of access, starting from launch.</p>
            </div>
            <div class="plan-save">
              You save ≈ $139.76 (about 58%) versus paying monthly later.
            </div>
            <a href="#" class="plan-cta">
              <span class="icon">⚡</span>
              Pre-order as Consumer – $100
            </a>
          </article>

          <!-- MAKER -->
          <article class="plan-card" id="support-maker">
            <div class="plan-tag">
              <span>Maker Plan (1 Product)</span>
            </div>
            <h3>Maker Plan (1 Product)</h3>
            <div class="plan-body">
              <p>
                For small manufacturers with one key product that they want to be fully visible,
                traceable, and connected to smart pricing and ESG data.
              </p>

              <p><strong>Future subscription</strong></p>
              <p>$29 / month</p>
              <p>2-year value: 24 × $29 = $696</p>

              <p><strong>Early supporter contribution</strong></p>
              <p>Pay $300 once today for 2 years of Maker access (1 product) from launch.</p>
            </div>
            <div class="plan-save">
              You save ≈ $396 (about 57%) compared to two years of future monthly payments.
            </div>
            <a href="#" class="plan-cta">
              <span class="icon">⚡</span>
              Pre-order as Maker – $300
            </a>
          </article>

          <!-- STORE -->
          <article class="plan-card" id="support-store">
            <div class="plan-tag">
              <span>Store Plan (50–200 products)</span>
            </div>
            <h3>Store Plan (50–200 Products)</h3>
            <div class="plan-body">
              <p>
                For retail stores that want to manage 50–200 products with dynamic pricing, live inventory,
                scan-to-pay checkout, and better shrinkage control.
              </p>

              <p><strong>Future subscription</strong></p>
              <p>$99 / month</p>
              <p>2-year value: 24 × $99 = $2,376</p>

              <p><strong>Early supporter contribution</strong></p>
              <p>Pay $1,000 once today for 2 years of Store-level access from launch.</p>
            </div>
            <div class="plan-save">
              You save ≈ $1,376 (about 58%), while helping build the very infrastructure you will use.
            </div>
            <a href="#" class="plan-cta">
              <span class="icon">⚡</span>
              Pre-order as Store – $1,000
            </a>
          </article>
        </section>

        <!-- LEGAL NOTE -->
        <section class="legal-note">
          <p><strong>Important legal note:</strong></p>
          <ul>
            <li>
              Each payment above is treated as a pre-order / early-support contribution linked to a future subscription
              for the corresponding user role (Consumer, Maker, Store).
            </li>
            <li>
              This is not an investment and not an offer to sell securities. No equity, profit sharing,
              or guaranteed financial return is offered.
            </li>
            <li>
              Exact access terms (2 years from launch, role-specific feature set) will be documented in user-facing
              terms of service before launch.
            </li>
            <li>Payments are processed securely via Stripe.</li>
          </ul>
          <p class="legal-note-strong">
            If the product is not launched within a reasonable timeframe, we will communicate options, including
            refunds or alternative arrangements, to early supporters.
          </p>
        </section>
      </section>

      <!-- RIGHT: PRODUCT STORY -->
      <section class="page-main-right" id="product-story">
        <!-- Product story · From manufacturer to consumer -->
        <section class="story-section">
          <div class="eyebrow">Product story · From manufacturer to consumer</div>
          <h1>Digital Labeling System (DLS)</h1>
          <h2>The Operating System for Physical Retail</h2>
        </section>

        <section class="story-section">
          <p>Retail is still managed with 20th-century infrastructure.</p>
          <p>But margins, regulation, competition, and consumer behavior are already 21st-century.</p>
          <p>Today, most retail still runs on:</p>
          <ul>
            <li>Static prices</li>
            <li>Blind inventory</li>
            <li>Manual markdowns</li>
            <li>Cashier dependency</li>
            <li>Paper receipts</li>
            <li>Fragmented compliance</li>
            <li>No real-time ESG</li>
          </ul>
          <p>
            This creates systemic financial leakage: Shrinkage. Expiration. Out-of-stocks.
            Pricing errors. Compliance risks.
          </p>
          <p>
            That’s why we are building Digital Labeling System (DLS) — the operating system for physical retail.
          </p>
        </section>

        <section class="story-section">
          <h2>What is DLS in Simple Terms?</h2>
          <p>We turn every physical product into a live digital asset.</p>
          <p>Each product receives:</p>
          <ul>
            <li>✅ A permanent digital identity</li>
            <li>✅ A real-time digital twin</li>
            <li>✅ AI-driven pricing and inventory logic</li>
            <li>✅ A built-in fiscal &amp; ESG record</li>
            <li>✅ Cashierless mobile checkout</li>
          </ul>
          <p>
            This means prices become algorithmic, inventory becomes real-time, expiration becomes predictable,
            fraud becomes detectable, compliance becomes automatic, and checkout works without cash desks.
            A smartphone becomes the primary retail terminal. No POS. No paper. No bottlenecks.
          </p>
        </section>

        <section class="story-section">
          <h2>Why This Is Not “Just Another Retail SaaS”</h2>
          <p>Whoever controls:</p>
          <ul>
            <li>Product identity</li>
            <li>Product price</li>
            <li>Product transaction</li>
            <li>Product compliance</li>
          </ul>
          <p>controls retail economics permanently. This is infrastructure, not a feature.</p>
        </section>

        <section class="story-section">
          <h2>How the System Works End-to-End</h2>
          <p>
            From Manufacturer to Retailer to Consumer — below is the full operational chain of DLS,
            exactly how the platform works in real life.
          </p>
        </section>

        <!-- 1️⃣ Manufacturer enters the system -->
        <section class="story-section">
          <h3>1️⃣ Manufacturer enters the system</h3>

          <h4>Step 1 — Product creation</h4>
          <p>
            The manufacturer creates a product inside the system: name, formulation, certificates,
            expiration rules, manufacturing details, ESG parameters.
          </p>
          <p>
            Each product instantly receives a unique permanent digital identity,
            a blockchain-ready lifecycle record, and a scannable QR / barcode.
          </p>

          <h4>Step 2 — Production update</h4>
          <p>
            Example: today the manufacturer produces 1,000 units and simply enters
            “Produced today: +1,000”. Inventory becomes 1,000 units available, every unit is
            digitally registered and trackable individually. Tomorrow another +500 —
            inventory becomes 1,500. No spreadsheets. No manual reconciliation.
          </p>

          <h4>Step 3 — Sales, shipments &amp; documents</h4>
          <p>
            Every shipment is handled in one interface: retailer requests, approvals,
            digital shipping documents, invoices, acceptance forms, and partner confirmations.
          </p>
          <p>
            The manufacturer always sees who ordered, how much was shipped, what remains in stock,
            who owes what, and which documents are signed — a real-time “Buy / Sell / Ship” control tower.
          </p>
          <p>Expert insight: blind logistics, shipment fraud, and post-factum disputes disappear.</p>
        </section>

        <!-- 2️⃣ Retailer enters the system -->
        <section class="story-section">
          <h3>2️⃣ Retailer enters the system</h3>

          <h4>Step 1 — Store network setup</h4>
          <p>
            The retailer can register one store or a full chain, add all locations, assign staff access,
            and map logistics routes. Each store becomes its own digital retail node.
          </p>

          <h4>Step 2 — Product procurement</h4>
          <p>
            Retailers create direct digital purchase requests to manufacturers, seeing live inventory,
            delivery windows, and pricing conditions. Orders are approved, shipped, and accepted digitally —
            and recorded permanently. No emails, no phone calls, no paper chaos.
          </p>

          <h4>Step 3 — AI-driven pricing</h4>
          <p>
            Retailers input logistics costs, storage, payroll, rent, and target margin.
            AI instantly calculates optimal retail prices, promotions, bulk discounts (“Buy 10 — cheaper”),
            and price sensitivity vs competitors. Retailers can accept, adjust, and launch promotions in one click.
            Price becomes a calculated strategy, not a guess.
          </p>

          <h4>Step 4 — Store without price tags</h4>
          <p>
            In the physical store there are no paper price tags, no manual updates, and no incorrect labels.
            Every shelf only needs the product with its QR / barcode. The digital price tag lives inside the product itself.
          </p>
        </section>

        <!-- 3️⃣ The consumer experience -->
        <section class="story-section">
          <h3>3️⃣ The consumer experience</h3>

          <h4>Step 1 — Entering the store</h4>
          <p>
            The customer enters any store, opens the DLS app, scans the store QR, and registers in two clicks
            or syncs an existing account. Instantly they receive a personal digital cabinet for this store.
          </p>

          <h4>Step 2 — Scanning products</h4>
          <p>
            At the shelf the customer scans any product and sees store name, real price, bulk discounts,
            expiration date, production date, full composition, instructions, certificates, and ESG data.
          </p>
          <p>
            Everything previously printed on packaging becomes digital, verified, and always up-to-date.
          </p>

          <h4>Step 3 — Self-managed cart</h4>
          <p>
            The customer scans, adds, adjusts quantity, and sees totals instantly — building the cart independently.
          </p>

          <h4>Step 4 — Online payment in the store</h4>
          <p>
            Walking to the exit, the customer pays directly in the app — with card, local currency, or crypto,
            and in the future with the platform’s own digital token.
          </p>

          <h4>Step 5 — Exit verification</h4>
          <p>
            At the exit the customer shows their cabinet number, staff verifies physically and digitally.
            A paper receipt can be printed in a second if needed; otherwise a legal digital fiscal receipt is stored.
          </p>

          <h4>Step 6 — Personal purchase history</h4>
          <p>
            The customer sees a map of visited stores, all past orders and receipts, and can re-order in one click,
            modify past baskets, order home delivery, and combine multiple stores—no need to go back for routine items.
          </p>

          <h4>Step 7 — AI-driven lifestyle orders</h4>
          <p>
            With a nutrition plan, training plan, or doctor’s prescription, the customer uploads it and AI builds
            a shopping order for several days or a week, splits it between stores or pharmacies, and adds medication
            reminders to the calendar. Retail becomes an intelligent assistant, not just a shelf.
          </p>
        </section>

        <!-- 4️⃣ Communication & services layer -->
        <section class="story-section">
          <h3>4️⃣ Communication &amp; services layer</h3>
          <p>
            Inside each product, DLS can host a real-time chat between manufacturer, retailer, and consumer
            for feedback, quality, support, and updates. On top of this, we can add advertising, brand engagement,
            personal offers, and loyalty programs.
          </p>
        </section>

        <!-- 5️⃣ Payments -->
        <section class="story-section">
          <h3>5️⃣ Payments: fiat, crypto &amp; future token economy</h3>
          <p>
            DLS supports USD and major fiat currencies, cards, local rails, and cryptocurrency payments.
            In the future, a native platform token will power instant exchange, loyalty conversion,
            token-based promotions and cashback — forming the foundation of a retail digital economy.
          </p>
        </section>

        <!-- What this delivers -->
        <section class="story-section">
          <h2>What this delivers</h2>
          <p>
            For manufacturers: total production visibility, live inventory, zero document chaos,
            digital compliance, direct retailer access.
          </p>
          <p>
            For retailers: dynamic AI pricing, real-time stock, no price-tag errors, cashierless flow,
            lower shrinkage, higher margin control.
          </p>
          <p>
            For consumers: full product transparency, faster shopping, no lines,
            digital receipts, smart reorders, health-driven orders.
          </p>
        </section>

        <!-- Why we are building this -->
        <section class="story-section">
          <h2>Why we are building this</h2>
          <p>
            We come from real retail and production, not slides: retail business ownership,
            printing &amp; labeling production, store operations, supplier and manufacturer workflows.
            We lived inside these problems. DLS turns that pain into permanent digital infrastructure.
          </p>
        </section>

        <!-- Result for humanity -->
        <section class="story-section">
          <h2>Result for humanity</h2>
          <p>
            If systems like DLS become global standard: less food waste, less fraud, less bureaucracy,
            lower prices, more transparent production, automated ESG, faster access to medicine,
            smarter cities, and smarter supply chains. This is not just retail evolution.
            It is the digital nervous system of physical commerce.
          </p>
        </section>

        <!-- What’s next -->
        <section class="story-section">
          <h2>What’s next</h2>
          <p>
            We are opening strategic retail pilots, hardware + AI integrations, crypto &amp; token payments,
            and early-stage strategic participation. If you are a retailer, manufacturer, logistics or payment partner,
            or strategic investor — this is exactly the control layer where the next decade of retail will be built.
            Let’s build it together.
          </p>
          <p><strong>DLS is in active build · Early supporter pre-order</strong></p>
        </section>
      </section>
    </main>

    <!-- FOUNDER -->
    <section class="founder-card" id="founder">
      <div class="founder-avatar">M</div>
      <div class="founder-main">
        <h3>Mikhail Shliachkov</h3>
        <div class="role">Founder &amp; CEO</div>

        <p><strong>Founder: Operational Expertise, Not Theory</strong></p>
        <p>
          Mikhail Shliachkov isn’t a theorist building retail technology from the outside.
          He’s an operational founder who has lived the problems DLS solves every day for over a decade.
        </p>

        <div class="founder-columns">
          <div class="founder-col">
            <h4>Retail Business Owner</h4>
            <p>
              Direct experience owning and operating retail businesses, understanding P&amp;L, margins,
              and operational challenges firsthand.
            </p>
          </div>
          <div class="founder-col">
            <h4>Printing &amp; Labeling Production</h4>
            <p>
              Deep expertise in label manufacturing, printing technology, and physical product identification systems.
            </p>
          </div>
          <div class="founder-col">
            <h4>Store Operations &amp; POS</h4>
            <p>
              Hands-on experience with point-of-sale systems, checkout operations,
              and in-store technology implementation.
            </p>
          </div>
          <div class="founder-col">
            <h4>Supplier &amp; Manufacturer Workflows</h4>
            <p>
              Understanding of supply chain dynamics, manufacturer relationships,
              and product lifecycle management.
            </p>
          </div>
        </div>

        <p class="founder-footer">
          This is not a theorist. This is an operational founder.
          Mikhail has managed a family business since 2012, experiencing every pain point DLS addresses.
          He knows what works, what doesn’t, and what retailers actually need — not what Silicon Valley thinks they need.
        </p>

        <p class="founder-footer">
          Team (in build): DLS is assembling a compact, execution-focused team across:
          product, AI/ML, retail integrations, and compliance. We actively welcome senior talent
          from retail, payments, logistics, and govtech who want to build shared infrastructure — not another short-term feature.
        </p>
      </div>
    </section>

    <!-- FOOTER -->
    <footer class="page-footer">
      <span>Digital Labeling System · DLS · Product Story &amp; Early Support</span>
      <span>All rights reserved</span>
    </footer>
  </div>
</body>
</html>
