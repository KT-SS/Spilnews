# Spilnews
Spilnews opvolgchecklist 19 mei 2026
<!DOCTYPE html>
<html lang="nl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Spilnews Opvolgplan — Week 19 mei</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&display=swap');

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0D0D0D;
    --bg-alt: #1A1A1A;
    --bg-card: #141414;
    --lime: #B4FF00;
    --lime-dim: rgba(180,255,0,0.08);
    --lime-mid: rgba(180,255,0,0.15);
    --white: #FFFFFF;
    --grey: #AAAAAA;
    --grey-dim: #444444;
    --border: #2A2A2A;
  }

  html { font-size: 16px; }

  body {
    background: var(--bg);
    color: var(--white);
    font-family: 'DM Mono', 'Courier New', monospace;
    min-height: 100vh;
    padding: 48px 24px 80px;
  }

  .page { max-width: 820px; margin: 0 auto; }

  /* HEADER */
  .header { margin-bottom: 48px; }

  .logo-row {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 32px;
  }

  .logo-mark {
    width: 32px;
    height: 32px;
    background: var(--lime);
    border-radius: 4px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .logo-mark svg { width: 18px; height: 18px; }

  .logo-text {
    font-size: 13px;
    font-weight: 500;
    color: var(--grey);
    letter-spacing: 0.12em;
    text-transform: uppercase;
  }

  .header h1 {
    font-family: Arial, sans-serif;
    font-size: 36px;
    font-weight: 700;
    color: var(--white);
    line-height: 1.1;
    margin-bottom: 10px;
  }

  .header h1 span { color: var(--lime); }

  .header-meta {
    font-size: 13px;
    color: var(--grey);
    margin-bottom: 28px;
  }

  /* PROGRESS */
  .progress-bar-wrap {
    background: var(--bg-alt);
    border-radius: 2px;
    height: 4px;
    margin-bottom: 8px;
    overflow: hidden;
  }

  .progress-bar-fill {
    height: 100%;
    background: var(--lime);
    border-radius: 2px;
    width: 0%;
    transition: width 0.4s ease;
  }

  .progress-label {
    font-size: 12px;
    color: var(--grey);
  }

  .progress-label span { color: var(--lime); font-weight: 500; }

  /* STATS ROW */
  .stats {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-bottom: 48px;
  }

  .stat {
    background: var(--bg-card);
    border: 0.5px solid var(--border);
    border-radius: 6px;
    padding: 16px;
  }

  .stat-num {
    font-family: Arial, sans-serif;
    font-size: 28px;
    font-weight: 700;
    color: var(--lime);
    line-height: 1;
    margin-bottom: 6px;
  }

  .stat-label {
    font-size: 11px;
    color: var(--grey);
    line-height: 1.4;
  }

  /* SECTION */
  .section { margin-bottom: 40px; }

  .section-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 14px;
    padding-bottom: 10px;
    border-bottom: 0.5px solid var(--border);
  }

  .section-dot {
    width: 8px;
    height: 8px;
    background: var(--lime);
    border-radius: 50%;
    flex-shrink: 0;
  }

  .section-title {
    font-family: Arial, sans-serif;
    font-size: 11px;
    font-weight: 700;
    color: var(--lime);
    letter-spacing: 0.12em;
    text-transform: uppercase;
  }

  .section-count {
    font-size: 11px;
    color: var(--grey-dim);
    margin-left: auto;
  }

  /* CARD */
  .card {
    background: var(--bg-card);
    border: 0.5px solid var(--border);
    border-radius: 8px;
    padding: 18px 20px;
    margin-bottom: 8px;
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 16px;
    align-items: start;
    transition: border-color 0.2s, background 0.2s;
    cursor: pointer;
  }

  .card:hover { border-color: #3a3a3a; }

  .card.done {
    background: rgba(180,255,0,0.03);
    border-color: rgba(180,255,0,0.2);
  }

  /* CHECKBOX */
  .checkbox {
    width: 20px;
    height: 20px;
    border: 1.5px solid var(--grey-dim);
    border-radius: 4px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    margin-top: 2px;
    transition: border-color 0.2s, background 0.2s;
  }

  .card.done .checkbox {
    background: var(--lime);
    border-color: var(--lime);
  }

  .checkbox svg {
    width: 12px;
    height: 12px;
    opacity: 0;
    transition: opacity 0.15s;
  }

  .card.done .checkbox svg { opacity: 1; }

  /* CARD BODY */
  .card-body { min-width: 0; }

  .card-top {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 12px;
    margin-bottom: 4px;
  }

  .card-name {
    font-family: Arial, sans-serif;
    font-size: 15px;
    font-weight: 700;
    color: var(--white);
    transition: color 0.2s;
  }

  .card.done .card-name {
    color: var(--grey);
    text-decoration: line-through;
    text-decoration-color: var(--grey-dim);
  }

  .card-org {
    font-size: 12px;
    color: var(--grey);
    margin-bottom: 8px;
  }

  .card.done .card-org { color: var(--grey-dim); }

  .badges {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
    flex-shrink: 0;
    align-items: flex-start;
  }

  .badge {
    font-size: 10px;
    font-weight: 500;
    padding: 3px 9px;
    border-radius: 20px;
    white-space: nowrap;
    letter-spacing: 0.04em;
    border: 0.5px solid transparent;
  }

  .badge-hot { background: rgba(255,80,60,0.12); color: #FF6B5B; border-color: rgba(255,80,60,0.25); }
  .badge-afspraak { background: rgba(180,255,0,0.1); color: var(--lime); border-color: rgba(180,255,0,0.25); }
  .badge-warm { background: rgba(255,180,0,0.1); color: #FFBB33; border-color: rgba(255,180,0,0.25); }
  .badge-mail { background: rgba(80,160,255,0.1); color: #7BB8FF; border-color: rgba(80,160,255,0.25); }
  .badge-door { background: rgba(180,120,255,0.1); color: #C49DFF; border-color: rgba(180,120,255,0.25); }
  .badge-sent { background: rgba(180,255,0,0.06); color: var(--lime); border-color: rgba(180,255,0,0.15); }

  .card-status {
    font-size: 12px;
    color: var(--grey);
    margin-bottom: 6px;
    line-height: 1.5;
  }

  .card-status strong { color: #CCCCCC; font-weight: 500; }

  .card-note {
    font-size: 12px;
    color: var(--grey);
    line-height: 1.6;
    margin-bottom: 10px;
  }

  .card.done .card-note { color: var(--grey-dim); }

  .card-phone {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 12px;
    color: var(--grey);
    margin-bottom: 10px;
    text-decoration: none;
    transition: color 0.15s;
  }

  .card-phone:hover { color: var(--lime); }
  .card-phone::before { content: '📞'; font-size: 11px; }
  .card.done .card-phone { color: var(--grey-dim); }

  .card-action {
    display: inline-block;
    font-size: 11px;
    font-weight: 500;
    padding: 4px 12px;
    border-radius: 4px;
    letter-spacing: 0.04em;
  }

  .action-bel { background: rgba(255,80,60,0.1); color: #FF6B5B; }
  .action-green { background: rgba(180,255,0,0.1); color: var(--lime); }
  .action-amber { background: rgba(255,180,0,0.1); color: #FFBB33; }
  .action-blue { background: rgba(80,160,255,0.1); color: #7BB8FF; }
  .action-purple { background: rgba(180,120,255,0.1); color: #C49DFF; }

  .card.done .card-action {
    opacity: 0.3;
    text-decoration: line-through;
  }

  /* UPDATE FIELD */
  .update-wrap {
    margin-top: 12px;
    border-top: 0.5px solid var(--border);
    padding-top: 10px;
  }

  .update-label {
    font-size: 10px;
    color: var(--grey-dim);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-bottom: 6px;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .update-label .update-dot {
    width: 5px;
    height: 5px;
    border-radius: 50%;
    background: var(--grey-dim);
    flex-shrink: 0;
    transition: background 0.2s;
  }

  .update-label.has-content .update-dot { background: var(--lime); }
  .update-label.has-content { color: var(--grey); }

  .update-field {
    width: 100%;
    background: var(--bg-alt);
    border: 0.5px solid var(--border);
    border-radius: 4px;
    color: var(--white);
    font-family: 'DM Mono', 'Courier New', monospace;
    font-size: 12px;
    line-height: 1.6;
    padding: 8px 10px;
    resize: none;
    min-height: 36px;
    overflow: hidden;
    transition: border-color 0.2s, min-height 0.15s;
    outline: none;
  }

  .update-field::placeholder { color: var(--grey-dim); }
  .update-field:focus { border-color: rgba(180,255,0,0.3); }
  .card.done .update-field { color: var(--grey); }

  /* FOOTER */
  .footer {
    margin-top: 56px;
    padding-top: 20px;
    border-top: 0.5px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .footer-brand {
    font-size: 11px;
    color: var(--grey-dim);
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .footer-brand span { color: var(--lime); }

  .reset-btn {
    background: none;
    border: 0.5px solid var(--border);
    color: var(--grey);
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    padding: 6px 14px;
    border-radius: 4px;
    cursor: pointer;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    transition: border-color 0.2s, color 0.2s;
  }

  .reset-btn:hover { border-color: var(--grey); color: var(--white); }

  @media (max-width: 600px) {
    .stats { grid-template-columns: repeat(2, 1fr); }
    .card-top { flex-direction: column; gap: 8px; }
    .header h1 { font-size: 26px; }
  }
</style>
</head>
<body>
<div class="page">

  <div class="header">
    <div class="logo-row">
      <div class="logo-mark">
        <svg viewBox="0 0 18 18" fill="none">
          <rect x="2" y="2" width="6" height="6" fill="#0D0D0D"/>
          <rect x="10" y="2" width="6" height="6" fill="#0D0D0D"/>
          <rect x="2" y="10" width="6" height="6" fill="#0D0D0D"/>
          <rect x="10" y="10" width="6" height="6" fill="#0D0D0D"/>
        </svg>
      </div>
      <span class="logo-text">Sprints &amp; Sneakers</span>
    </div>

    <h1>Spilnews <span>Opvolgplan</span></h1>
    <p class="header-meta">Week 19 mei 2026 &nbsp;/&nbsp; Ken + Birgit &nbsp;/&nbsp; Iedereen heeft een info mail ontvangen</p>

    <div class="progress-bar-wrap">
      <div class="progress-bar-fill" id="progressBar"></div>
    </div>
    <p class="progress-label"><span id="progressText">0 / 0</span> acties afgerond</p>
  </div>

  <div class="stats">
    <div class="stat"><div class="stat-num">3</div><div class="stat-label">Afspraken bevestigen</div></div>
    <div class="stat"><div class="stat-num">8</div><div class="stat-label">Nabellen, mail check</div></div>
    <div class="stat"><div class="stat-num">4</div><div class="stat-label">Doorverwijzing uitzoeken</div></div>
    <div class="stat"><div class="stat-num">1</div><div class="stat-label">WhatsApp / LinkedIn</div></div>
  </div>

  <!-- BLOK 1 -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot"></div>
      <span class="section-title">Blok 1 — Afspraken bevestigen en voorbereiden</span>
      <span class="section-count" id="count-1"></span>
    </div>

    <div class="card" onclick="toggle(this)" data-block="1">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Mirjam Groenestein</div>
            <div class="card-org">HVA</div>
          </div>
          <div class="badges"><span class="badge badge-afspraak">Afspraak 1 juli</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Wil mogelijkheden verkennen zodra drukte eind schooljaar voorbij is</strong></div>
        <div class="card-note">Meeting staat voor 1 juli. Birgit belt haar vooraf voor een korte kennismaking en om de tijd vast te prikken. Goed moment nu het schooljaar bijna afloopt.</div>
        <a class="card-phone" href="tel:+31621155721" onclick="event.stopPropagation()">+31621155721</a>
        <span class="card-action action-green">Birgit belt voor kennismaking + tijdbevestiging</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="1">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Ton van Aar</div>
            <div class="card-org">ROC Nijmegen</div>
          </div>
          <div class="badges"><span class="badge badge-afspraak">Afspraak</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Geinteresseerd in lokale influencer of campagne</strong></div>
        <div class="card-note">Meeting gepland. Bereidt de pitch voor op regionaal bereik: influencers rondom Nijmegen en Land van Cuijk zijn de concrete invalshoek.</div>
        <a class="card-phone" href="tel:+31681172330" onclick="event.stopPropagation()">+31681172330</a>
        <span class="card-action action-green">Meeting bevestigen + lokale influencer case meenemen</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="1">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Munstermedia</div>
            <div class="card-org">Mediabureau</div>
          </div>
          <div class="badges"><span class="badge badge-afspraak">Afspraak</span><span class="badge badge-hot">Let op: indirect</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Geen directe afnemer, maar klanten willen Gen Z aantrekken</strong></div>
        <div class="card-note">Potentieel als referral of reseller, niet als directe klant. Houd de meeting strak en stuur naar een concrete next step. Praat veel, dus kader het gesprek van tevoren.</div>
        <span class="card-action action-amber">Meeting met partnerframe, niet als vendor pitchen</span>
      </div>
    </div>
  </div>

  <!-- BLOK 2 -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot"></div>
      <span class="section-title">Blok 2 — Nabellen: hoe is de mail geland?</span>
      <span class="section-count" id="count-2"></span>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Iris van der Valk</div>
            <div class="card-org">Het Concertgebouw — Social Media Manager</div>
          </div>
          <div class="badges"><span class="badge badge-hot">Urgent TB deze week</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Vond de propositie interessant, mail verstuurd, terugbellen deze week</strong></div>
        <div class="card-note">Zelf als "TB deze week" genoteerd: dit is de meest acute call op de lijst. Vraag hoe de mail geland is en of er vragen zijn.</div>
        <a class="card-phone" href="tel:+31648542288" onclick="event.stopPropagation()">+31648542288</a>
        <span class="card-action action-bel">Bellen deze week: hoe is de mail geland?</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Merel Bus</div>
            <div class="card-org">Inholland — Projectleider merkpropositie jongeren</div>
          </div>
          <div class="badges"><span class="badge badge-hot">5 weken open</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Was geinteresseerd, mail verstuurd, geen reactie</strong></div>
        <div class="card-note">Juiste beslisser intern. Langst openstaande warme lead op de lijst. Bel en vraag of de mail is overgekomen en of er vragen zijn.</div>
        <a class="card-phone" href="tel:+31641265343" onclick="event.stopPropagation()">+31641265343</a>
        <span class="card-action action-bel">Bellen: mail geland? Vragen?</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Richelle Oostrom</div>
            <div class="card-org">Belsimpel — Partner Marketing Manager</div>
          </div>
          <div class="badges"><span class="badge badge-warm">Terugbellen 1 juni</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Terug van vakantie 1 juni, heeft zelf aangegeven dan te reageren</strong></div>
        <div class="card-note">Meest voorspelbare conversie op de lijst. Zet een reminder voor maandag 1 juni. Vraag of ze de mail heeft kunnen lezen en hoe die geland is.</div>
        <a class="card-phone" href="tel:+31655597939" onclick="event.stopPropagation()">+31655597939</a>
        <span class="card-action action-bel">Bellen 1 juni: mail gelezen? Vragen?</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Allard Massar</div>
            <div class="card-org">Belsimpel — Partner Marketing Manager</div>
          </div>
          <div class="badges"><span class="badge badge-warm">Geinteresseerd</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Wilde intern bespreken, wacht op reactie</strong></div>
        <div class="card-note">Koppel aan Richelle Oostrom call op 1 juni: twee Belsimpel contacten, één account. Vraag of het intern al besproken is.</div>
        <a class="card-phone" href="tel:+31640149560" onclick="event.stopPropagation()">+31640149560</a>
        <span class="card-action action-bel">Bellen: intern besproken? Koppel aan Richelle</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Matthijs Wols</div>
            <div class="card-org">The July — Growth Marketing Manager</div>
          </div>
          <div class="badges"><span class="badge badge-warm">Geinteresseerd</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Erg geinteresseerd, speelt door aan brand manager</strong></div>
        <div class="card-note">Enthousiast aan de telefoon. Vraag of de brand manager de mail heeft ontvangen en wat de reactie was.</div>
        <a class="card-phone" href="tel:+31622720858" onclick="event.stopPropagation()">+31622720858</a>
        <span class="card-action action-bel">Bellen: is het doorgegeven aan brand manager?</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Luuk Molenschot</div>
            <div class="card-org">Awakenings — Brand Partnerships Manager</div>
          </div>
          <div class="badges"><span class="badge badge-warm">Geinteresseerd</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Geinteresseerd, gaat info intern doorspelen</strong></div>
        <div class="card-note">Mail verstuurd. Bel om te checken of de mail is geland en of hij het al intern heeft gedeeld.</div>
        <a class="card-phone" href="tel:+31653740489" onclick="event.stopPropagation()">+31653740489</a>
        <span class="card-action action-bel">Bellen: mail geland? Intern gedeeld?</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Nienke Jolien Norden</div>
            <div class="card-org">GoldRepublic — Head of Production, Media &amp; Events</div>
          </div>
          <div class="badges"><span class="badge badge-warm">Mailverzoek</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Klonk niet overtuigd maar wilde info mail, zei zelf terug te bellen</strong></div>
        <div class="card-note">Lauwe lead. Als ze zelf niet terugbelt, één keer nabellen en daarna loslaten.</div>
        <a class="card-phone" href="tel:+31655597138" onclick="event.stopPropagation()">+31655597138</a>
        <span class="card-action action-bel">1x nabellen: mail geland? Anders loslaten</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Kim Lokhorst</div>
            <div class="card-org">Nederlands Jeugdinstituut — Manager Social Media</div>
          </div>
          <div class="badges"><span class="badge badge-warm">Geinteresseerd</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Wilde meer info, niet blij met prive belletje</strong></div>
        <div class="card-note">Niet opnieuw bellen op hetzelfde nummer. Stuur een LinkedIn bericht of mail als follow-up: is de mail overgekomen?</div>
        <a class="card-phone" href="tel:+31610852101" onclick="event.stopPropagation()">+31610852101</a>
        <span class="card-action action-blue">LinkedIn of mail: niet bellen</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Cedrique Aardoom</div>
            <div class="card-org">ID&amp;T — Brand Partnerships Manager</div>
          </div>
          <div class="badges"><span class="badge badge-mail">Mailverzoek</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Was geinteresseerd, wil zelf contact opnemen, niet andersom</strong></div>
        <div class="card-note">Expliciete voorkeur om zelf te bellen. Stuur een vriendelijke reminder mail en laat hem de volgende stap zetten.</div>
        <a class="card-phone" href="tel:+31641532456" onclick="event.stopPropagation()">+31641532456</a>
        <span class="card-action action-blue">Reminder mail: niet bellen</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Cansu Ozuysal</div>
            <div class="card-org">PPHE Hotel Group — Paid Media</div>
          </div>
          <div class="badges"><span class="badge badge-warm">Contactpersoon doorsturen</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Geinteresseerd, geeft interne contactpersoon door, nog niet ontvangen</strong></div>
        <div class="card-note">Cansu was een maand weg. Die maand is voorbij. Ze zou de juiste interne contactpersoon doorgeven: dat is nog niet gebeurd.</div>
        <a class="card-phone" href="tel:+31642749623" onclick="event.stopPropagation()">+31642749623</a>
        <span class="card-action action-bel">Cansu bellen: wie is de juiste persoon bij PPHE?</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Ilse Westrik</div>
            <div class="card-org">Plants &amp; Flowers Foundation — Manager B2C</div>
          </div>
          <div class="badges"><span class="badge badge-mail">Info mail verstuurd</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Gen Z niet primaire doelgroep, maar wil meer info</strong></div>
        <div class="card-note">Lauw maar open. Mail is verstuurd. Bel om te vragen hoe die geland is en plan een callback in.</div>
        <a class="card-phone" href="tel:+31647068829" onclick="event.stopPropagation()">+31647068829</a>
        <span class="card-action action-bel">Nabellen: mail geland? Callback inplannen</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="2">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Christa Hemelaar</div>
            <div class="card-org">SUSA — Senior Digital Marketeer</div>
          </div>
          <div class="badges"><span class="badge badge-mail">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Niet de juiste persoon, laat het vallen bij collega's, wilde info mail</strong></div>
        <div class="card-note">Lage directe kans maar info mail is verstuurd. Als er geen reactie komt volgende week, loslaten.</div>
        <a class="card-phone" href="tel:+31610103736" onclick="event.stopPropagation()">+31610103736</a>
        <span class="card-action action-bel">1x nabellen: mail geland? Anders loslaten</span>
      </div>
    </div>
  </div>

  <!-- BLOK 3 -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot"></div>
      <span class="section-title">Blok 3 — Doorverwijzingen: contactpersoon nog vinden</span>
      <span class="section-count" id="count-3"></span>
    </div>

    <div class="card" onclick="toggle(this)" data-block="3">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Matthijs (achternaam onbekend)</div>
            <div class="card-org">Wie Leest Heeft Een Goed Verhaal — Campagnemanager</div>
          </div>
          <div class="badges"><span class="badge badge-door">Doorverwezen via Stichting Lezen</span></div>
        </div>
        <div class="card-status">Status: <strong>Koopt ads in voor Gen Z, contactgegevens nog niet gevonden</strong></div>
        <div class="card-note">Warme ingang via Barbara Wormgoor. Zoek Matthijs op LinkedIn via de organisatienaam en functietitel campagnemanager.</div>
        <span class="card-action action-purple">LinkedIn: zoek Matthijs bij deze organisatie</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="3">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">ROC van Amsterdam — Johanna / Chantal / Lotje</div>
            <div class="card-org">ROC van Amsterdam</div>
          </div>
          <div class="badges"><span class="badge badge-door">Onbereikbaar, 5+ pogingen</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Interesse bevestigd via Chantal, niemand neemt op</strong></div>
        <div class="card-note">Mail is verstuurd maar bellen werkt niet. Probeer een LinkedIn DM aan Johanna of Chantal als andere ingang.</div>
        <a class="card-phone" href="tel:+31647410183" onclick="event.stopPropagation()">+31647410183 (Chantal)</a>
        <a class="card-phone" href="tel:+31627359500" onclick="event.stopPropagation()">+31627359500 (Lotje)</a>
        <span class="card-action action-purple">LinkedIn DM: mail geland? Kunnen we iets plannen?</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="3">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">Rodrigo Aleman</div>
            <div class="card-org">Startupbootcamp — niet meer werkzaam</div>
          </div>
          <div class="badges"><span class="badge badge-door">Doorverwijzing via WhatsApp</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Stuurt WhatsApp door naar ex-collega's bij Startupbootcamp</strong></div>
        <div class="card-note">Warme ingang via oud-medewerker. Doe dit deze week: dit koelt snel af als je het laat liggen.</div>
        <a class="card-phone" href="tel:+34644498229" onclick="event.stopPropagation()">+34644498229</a>
        <span class="card-action action-amber">WhatsApp sturen aan Rodrigo deze week nog</span>
      </div>
    </div>

    <div class="card" onclick="toggle(this)" data-block="3">
      <div class="checkbox"><svg viewBox="0 0 12 12" fill="none"><polyline points="2,6 5,9 10,3" stroke="#0D0D0D" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
      <div class="card-body">
        <div class="card-top">
          <div>
            <div class="card-name">RAI Amsterdam — nieuwe contactpersoon</div>
            <div class="card-org">RAI Amsterdam</div>
          </div>
          <div class="badges"><span class="badge badge-door">Contactpersoon vertrokken</span><span class="badge badge-sent">Mail verstuurd</span></div>
        </div>
        <div class="card-status">Status: <strong>Tessa verlaat RAI, Sander wacht op mail, nieuwe ingang nodig</strong></div>
        <div class="card-note">Beide bekende contacten zijn weg of vertrekkend. Mail is verstuurd maar komt bij niemand terecht. Zoek via LinkedIn wie nu verantwoordelijk is voor performance marketing of partnerships.</div>
        <a class="card-phone" href="tel:+31628432563" onclick="event.stopPropagation()">+31628432563 (Sander Bogaard)</a>
        <span class="card-action action-purple">LinkedIn: nieuwe contactpersoon RAI Amsterdam vinden</span>
      </div>
    </div>
  </div>

  <div class="footer">
    <span class="footer-brand"><span>S&amp;S</span> / Spilnews / Week 19 mei 2026</span>
    <button class="reset-btn" onclick="resetAll()">Reset alles</button>
  </div>

</div>

<script>
  const STORAGE_KEY = 'ss_spilnews_checklist';
  const NOTES_KEY = 'ss_spilnews_notes';

  function getState() {
    try { return JSON.parse(localStorage.getItem(STORAGE_KEY)) || {}; } catch { return {}; }
  }
  function saveState(state) {
    try { localStorage.setItem(STORAGE_KEY, JSON.stringify(state)); } catch {}
  }
  function getNotes() {
    try { return JSON.parse(localStorage.getItem(NOTES_KEY)) || {}; } catch { return {}; }
  }
  function saveNotes(notes) {
    try { localStorage.setItem(NOTES_KEY, JSON.stringify(notes)); } catch {}
  }

  function toggle(card) {
    card.classList.toggle('done');
    persistState();
    updateProgress();
    updateBlockCounts();
  }

  function persistState() {
    const cards = document.querySelectorAll('.card');
    const state = {};
    cards.forEach((c, i) => { state[i] = c.classList.contains('done'); });
    saveState(state);
  }

  function restoreState() {
    const state = getState();
    const notes = getNotes();
    const cards = document.querySelectorAll('.card');
    cards.forEach((c, i) => {
      if (state[i]) c.classList.add('done');
      const ta = c.querySelector('.update-field');
      const lbl = c.querySelector('.update-label');
      if (ta && notes[i]) {
        ta.value = notes[i];
        autoGrow(ta);
        if (notes[i].trim()) lbl.classList.add('has-content');
      }
    });
  }

  function autoGrow(el) {
    el.style.height = 'auto';
    el.style.height = Math.max(36, el.scrollHeight) + 'px';
  }

  function initUpdateFields() {
    const cards = document.querySelectorAll('.card');
    cards.forEach((card, i) => {
      const body = card.querySelector('.card-body');

      const wrap = document.createElement('div');
      wrap.className = 'update-wrap';

      const label = document.createElement('div');
      label.className = 'update-label';
      label.innerHTML = '<span class="update-dot"></span> Laatste update / opmerking';

      const ta = document.createElement('textarea');
      ta.className = 'update-field';
      ta.rows = 1;
      ta.placeholder = 'Voeg hier een update of opmerking toe...';

      ta.addEventListener('click', e => e.stopPropagation());
      ta.addEventListener('keydown', e => e.stopPropagation());

      ta.addEventListener('input', () => {
        autoGrow(ta);
        const notes = getNotes();
        notes[i] = ta.value;
        saveNotes(notes);
        if (ta.value.trim()) {
          label.classList.add('has-content');
        } else {
          label.classList.remove('has-content');
        }
      });

      wrap.appendChild(label);
      wrap.appendChild(ta);
      body.appendChild(wrap);
    });
  }

  function updateProgress() {
    const cards = document.querySelectorAll('.card');
    const done = document.querySelectorAll('.card.done').length;
    const total = cards.length;
    const pct = total ? Math.round((done / total) * 100) : 0;
    document.getElementById('progressBar').style.width = pct + '%';
    document.getElementById('progressText').textContent = done + ' / ' + total;
  }

  function updateBlockCounts() {
    [1, 2, 3].forEach(b => {
      const all = document.querySelectorAll('[data-block="' + b + '"]');
      const done = document.querySelectorAll('[data-block="' + b + '"].done');
      const el = document.getElementById('count-' + b);
      if (el) el.textContent = done.length + ' / ' + all.length;
    });
  }

  function resetAll() {
    document.querySelectorAll('.card').forEach(c => c.classList.remove('done'));
    document.querySelectorAll('.update-field').forEach(ta => {
      ta.value = '';
      ta.style.height = '36px';
      const lbl = ta.closest('.update-wrap').querySelector('.update-label');
      if (lbl) lbl.classList.remove('has-content');
    });
    saveState({});
    saveNotes({});
    updateProgress();
    updateBlockCounts();
  }

  initUpdateFields();
  restoreState();
  updateProgress();
  updateBlockCounts();
</script>
</body>
</html>
