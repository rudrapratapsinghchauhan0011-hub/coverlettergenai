<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cover Letter Generator — Rudra Pratap Singh</title>
<style>
:root{
  --ink:#08111f;--deep:#0d1c32;--card:#101e35;
  --gold:#b8975a;--gold2:#d4b37a;--gold3:#e8cfa0;
  --muted:#6a7a92;--white:#ffffff;
  --border:rgba(184,151,90,.18);--border2:rgba(184,151,90,.38);
  --green:#2ecc71;--radius:4px;
}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{
  font-family:'Gill Sans','Optima','Segoe UI','Helvetica Neue',Arial,sans-serif;
  background:var(--ink);color:var(--white);min-height:100vh;
}

/* ── HEADER ── */
header{
  background:rgba(8,17,31,.95);
  border-bottom:1px solid var(--border);
  padding:1.5rem 5%;
  display:flex;align-items:center;justify-content:space-between;
  position:sticky;top:0;z-index:100;backdrop-filter:blur(12px);
}
.logo{
  font-family:'Didot','Bodoni MT',Georgia,serif;
  font-size:1.2rem;font-weight:700;color:var(--gold);letter-spacing:.08em;
}
.logo span{font-weight:300;color:rgba(255,255,255,.5);font-size:.85rem;margin-left:.8rem;}

/* ── MAIN LAYOUT ── */
.container{max-width:1100px;margin:0 auto;padding:3rem 5%;}

.page-title{
  font-family:'Didot','Bodoni MT',Georgia,serif;
  font-size:clamp(2rem,4vw,2.8rem);font-weight:700;
  color:var(--white);margin-bottom:.5rem;
}
.page-title em{color:var(--gold);font-style:italic;}
.page-sub{font-size:.92rem;color:var(--muted);margin-bottom:3rem;font-weight:300;}

/* ── TWO COL ── */
.layout{display:grid;grid-template-columns:380px 1fr;gap:2rem;align-items:start;}

/* ── LEFT PANEL ── */
.panel{
  background:var(--deep);border:1px solid var(--border);
  border-radius:var(--radius);padding:1.8rem;
  position:sticky;top:90px;
}
.panel-title{
  font-family:'Didot','Bodoni MT',Georgia,serif;
  font-size:1rem;font-weight:700;color:var(--gold);
  margin-bottom:1.5rem;letter-spacing:.05em;
  text-transform:uppercase;font-size:.8rem;
}

.field{margin-bottom:1.3rem;}
label{
  display:block;font-size:.72rem;letter-spacing:.12em;
  text-transform:uppercase;color:var(--muted);margin-bottom:.5rem;
}
input,select,textarea{
  width:100%;background:var(--card);
  border:1px solid var(--border);border-radius:var(--radius);
  color:var(--white);padding:.75rem 1rem;
  font-family:inherit;font-size:.88rem;
  transition:border-color .3s;outline:none;
  -webkit-appearance:none;
}
input:focus,select:focus,textarea:focus{border-color:var(--gold);}
select option{background:var(--card);}
textarea{resize:vertical;min-height:80px;}

/* company type cards */
.type-grid{display:grid;grid-template-columns:1fr 1fr;gap:.6rem;margin-top:.3rem;}
.type-card{
  background:var(--card);border:1px solid var(--border);
  border-radius:var(--radius);padding:.7rem .8rem;
  cursor:pointer;transition:all .25s;text-align:center;
}
.type-card:hover{border-color:var(--gold2);}
.type-card.active{background:rgba(184,151,90,.12);border-color:var(--gold);box-shadow:0 0 0 1px rgba(184,151,90,.15);}
.type-card .tc-icon{font-size:1.3rem;margin-bottom:.3rem;}
.type-card .tc-name{font-size:.72rem;font-weight:600;color:var(--white);letter-spacing:.03em;}
.type-card .tc-ex{font-size:.65rem;color:var(--muted);margin-top:.15rem;}

/* tone pills */
.tone-row{display:flex;flex-wrap:wrap;gap:.5rem;margin-top:.3rem;}
.tone-pill{
  border:1px solid var(--border);border-radius:20px;
  padding:.3rem .85rem;font-size:.72rem;cursor:pointer;
  color:rgba(255,255,255,.55);transition:all .25s;
}
.tone-pill.active{background:var(--gold);color:var(--ink);border-color:var(--gold);font-weight:600;}

.gen-btn{
  width:100%;margin-top:1.5rem;
  background:var(--gold);color:var(--ink);
  border:none;border-radius:var(--radius);
  padding:1rem;font-size:.85rem;font-weight:700;
  letter-spacing:.1em;text-transform:uppercase;
  cursor:pointer;transition:all .3s;
  display:flex;align-items:center;justify-content:center;gap:.6rem;
}
.gen-btn:hover{background:var(--gold2);transform:translateY(-2px);box-shadow:0 10px 25px rgba(184,151,90,.25);}
.gen-btn:disabled{opacity:.5;cursor:not-allowed;transform:none;}

/* ── RIGHT PANEL ── */
.output-panel{
  background:var(--deep);border:1px solid var(--border);
  border-radius:var(--radius);min-height:600px;
  display:flex;flex-direction:column;
}

.output-header{
  padding:1.2rem 1.8rem;
  border-bottom:1px solid var(--border);
  display:flex;align-items:center;justify-content:space-between;
  flex-wrap:wrap;gap:.8rem;
}
.output-title{
  font-size:.78rem;letter-spacing:.15em;
  text-transform:uppercase;color:var(--gold);font-weight:600;
}
.output-actions{display:flex;gap:.7rem;flex-wrap:wrap;}
.act-btn{
  border:1px solid var(--border2);background:transparent;
  color:rgba(255,255,255,.7);border-radius:var(--radius);
  padding:.45rem 1rem;font-size:.72rem;font-weight:500;
  cursor:pointer;transition:all .25s;letter-spacing:.05em;
  font-family:inherit;
}
.act-btn:hover{border-color:var(--gold);color:var(--gold);}
.act-btn.copy-done{background:rgba(46,204,113,.1);border-color:var(--green);color:var(--green);}

.output-body{
  padding:2rem 2.2rem;flex:1;
  font-size:.92rem;line-height:1.85;
  color:rgba(255,255,255,.82);font-weight:300;
  white-space:pre-wrap;
}

/* empty state */
.empty-state{
  display:flex;flex-direction:column;align-items:center;
  justify-content:center;flex:1;
  padding:3rem;text-align:center;gap:1rem;
}
.empty-icon{font-size:3rem;opacity:.3;}
.empty-text{font-size:.9rem;color:var(--muted);max-width:300px;line-height:1.7;}

/* typing cursor */
.typing::after{
  content:'|';animation:blink .7s infinite;color:var(--gold);
}
@keyframes blink{0%,100%{opacity:1;}50%{opacity:0;}}

/* loading dots */
.loading-dots span{
  display:inline-block;width:6px;height:6px;
  background:var(--gold);border-radius:50%;margin:0 2px;
  animation:dot .9s infinite;
}
.loading-dots span:nth-child(2){animation-delay:.2s;}
.loading-dots span:nth-child(3){animation-delay:.4s;}
@keyframes dot{0%,100%{transform:translateY(0);}50%{transform:translateY(-6px);}}

/* word count badge */
.wc-badge{
  font-size:.7rem;color:var(--muted);
  padding:.3rem .7rem;border:1px solid var(--border);
  border-radius:20px;
}

/* print styles */
@media print{
  header,.panel,.output-header,.output-actions{display:none!important;}
  .layout{grid-template-columns:1fr;}
  .output-panel{border:none;min-height:auto;}
  .output-body{color:#111;font-size:11pt;line-height:1.7;}
  body{background:#fff;}
}

@media(max-width:800px){
  .layout{grid-template-columns:1fr;}
  .panel{position:static;}
}
</style>
</head>
<body>

<header>
  <div class="logo">RPS <span>Cover Letter Generator</span></div>
  <div style="font-size:.75rem;color:var(--muted);">Rudra Pratap Singh · MBA Finance & Analytics</div>
</header>

<div class="container">
  <h1 class="page-title">Cover Letter <em>Generator</em></h1>
  <p class="page-sub">Select the company type, add the role details, and generate a tailored cover letter in seconds.</p>

  <div class="layout">

    <!-- LEFT: CONTROLS -->
    <div class="panel">
      <div class="panel-title">⚙️ Customise Your Letter</div>

      <!-- Company Type -->
      <div class="field">
        <label>Company Type</label>
        <div class="type-grid">
          <div class="type-card active" data-type="big4" onclick="selectType(this)">
            <div class="tc-icon">🏢</div>
            <div class="tc-name">Big 4</div>
            <div class="tc-ex">Deloitte, KPMG, EY, PwC</div>
          </div>
          <div class="type-card" data-type="consulting" onclick="selectType(this)">
            <div class="tc-icon">📊</div>
            <div class="tc-name">Consulting</div>
            <div class="tc-ex">Bain, McKinsey, BCG</div>
          </div>
          <div class="type-card" data-type="investment" onclick="selectType(this)">
            <div class="tc-icon">💹</div>
            <div class="tc-name">Investment Banking</div>
            <div class="tc-ex">Goldman, JPMorgan, Citi</div>
          </div>
          <div class="type-card" data-type="tech" onclick="selectType(this)">
            <div class="tc-icon">💻</div>
            <div class="tc-name">Tech / Product</div>
            <div class="tc-ex">Google, Microsoft, Amazon</div>
          </div>
          <div class="type-card" data-type="startup" onclick="selectType(this)">
            <div class="tc-icon">🚀</div>
            <div class="tc-name">Startup / FinTech</div>
            <div class="tc-ex">Razorpay, CRED, Zerodha</div>
          </div>
          <div class="type-card" data-type="nbfc" onclick="selectType(this)">
            <div class="tc-icon">🏦</div>
            <div class="tc-name">NBFC / Banking</div>
            <div class="tc-ex">HDFC, Bajaj, Aditya Birla</div>
          </div>
          <div class="type-card" data-type="fmcg" onclick="selectType(this)">
            <div class="tc-icon">🛒</div>
            <div class="tc-name">FMCG / Strategy</div>
            <div class="tc-ex">HUL, ITC, P&G, Nestle</div>
          </div>
          <div class="type-card" data-type="analytics" onclick="selectType(this)">
            <div class="tc-icon">📈</div>
            <div class="tc-name">Analytics / Data</div>
            <div class="tc-ex">Mu Sigma, Tiger Analytics</div>
          </div>
        </div>
      </div>

      <!-- Company Name -->
      <div class="field">
        <label>Company Name</label>
        <input type="text" id="companyName" placeholder="e.g. Deloitte India" />
      </div>

      <!-- Role -->
      <div class="field">
        <label>Role / Position</label>
        <input type="text" id="roleTitle" placeholder="e.g. Business Analyst Intern" />
      </div>

      <!-- Hiring Manager -->
      <div class="field">
        <label>Hiring Manager Name <span style="color:var(--muted);font-size:.65rem;">(optional)</span></label>
        <input type="text" id="hiringManager" placeholder="e.g. Mr. Sharma / Leave blank" />
      </div>

      <!-- Specific skill to highlight -->
      <div class="field">
        <label>Key Skill to Highlight</label>
        <select id="keySkill">
          <option value="financial modeling">Financial Modeling & Valuation</option>
          <option value="business analytics">Business Analytics & Power BI</option>
          <option value="market research">Market Research & Strategy</option>
          <option value="sales and crm">Sales & CRM Experience (HDB)</option>
          <option value="stakeholder management">Stakeholder Management</option>
          <option value="product management">Product Management</option>
          <option value="credit risk">Credit Risk & NBFC Operations</option>
        </select>
      </div>

      <!-- Tone -->
      <div class="field">
        <label>Tone</label>
        <div class="tone-row">
          <div class="tone-pill active" data-tone="professional" onclick="selectTone(this)">Professional</div>
          <div class="tone-pill" data-tone="confident" onclick="selectTone(this)">Confident</div>
          <div class="tone-pill" data-tone="enthusiastic" onclick="selectTone(this)">Enthusiastic</div>
          <div class="tone-pill" data-tone="concise" onclick="selectTone(this)">Concise</div>
        </div>
      </div>

      <!-- Extra note -->
      <div class="field">
        <label>Any Specific Point to Include? <span style="color:var(--muted);font-size:.65rem;">(optional)</span></label>
        <textarea id="extraNote" placeholder="e.g. I was referred by John, I saw this role at a campus event..."></textarea>
      </div>

      <button class="gen-btn" id="genBtn" onclick="generateLetter()">
        <span id="btnIcon">✨</span>
        <span id="btnText">Generate Cover Letter</span>
      </button>
    </div>

    <!-- RIGHT: OUTPUT -->
    <div class="output-panel" id="outputPanel">
      <div class="output-header">
        <div class="output-title">Generated Cover Letter</div>
        <div class="output-actions">
          <span class="wc-badge" id="wordCount">0 words</span>
          <button class="act-btn" onclick="copyLetter()" id="copyBtn">📋 Copy</button>
          <button class="act-btn" onclick="printLetter()">🖨️ Print</button>
          <button class="act-btn" onclick="downloadLetter()">⬇ Download .txt</button>
        </div>
      </div>

      <div class="empty-state" id="emptyState">
        <div class="empty-icon">✉️</div>
        <div class="empty-text">Fill in the details on the left and click <strong style="color:var(--gold)">Generate Cover Letter</strong> to create your personalised letter instantly.</div>
      </div>

      <div class="output-body" id="outputBody" style="display:none;"></div>
    </div>

  </div>
</div>

<script>
// ── STATE ──
let selectedType = 'big4';
let selectedTone = 'professional';
let currentLetter = '';

function selectType(el) {
  document.querySelectorAll('.type-card').forEach(c => c.classList.remove('active'));
  el.classList.add('active');
  selectedType = el.dataset.type;
}
function selectTone(el) {
  document.querySelectorAll('.tone-pill').forEach(p => p.classList.remove('active'));
  el.classList.add('active');
  selectedTone = el.dataset.tone;
}

// ── PROFILE DATA ──
const profile = {
  name: 'Rudra Pratap Singh',
  email: 'rudrapratapsinghchauhan0011@gmail.com',
  phone: '+91 896-066-9802',
  linkedin: 'linkedin.com/in/rudrapratapsingh0001',
  location: 'Gurugram, Haryana, India',
  mba: 'MBA in Finance & Business Analytics, IILM University Gurugram (2025–2027)',
  bba: 'BBA in Finance, Prestige Institute of Management & Research, Gwalior — CGPA 7.4/10',
  cat: 'CAT 2024: 78 percentile',
  nmat: 'NMAT 2024: 227 score',
  exp1: 'Sales Executive at HDB Financial Services Ltd. (Dec 2022 – Sep 2023) — managed 20–30+ customer interactions weekly, 100% regulatory compliance, cross-functional collaboration',
  exp2: 'Freelance Business & Market Researcher (Aug 2024 – Present) — SME pricing analysis, cost optimisation, business analytics frameworks',
  exp3: 'Project Intern at Shramik Bharti NGO (Aug–Sep 2022) — stakeholder engagement with 200+ beneficiaries, impact reporting, public policy analysis',
  certs: 'Financial Analyst Certification (Udemy), Product Management Insights (LinkedIn), Google Digital Training Trainer (trained 30+), Digital Security Training (Google × Asia Centre)',
  skills: 'Financial Modeling, Valuation (DCF/Comps), Power BI, MS Excel (Advanced), CRM Systems, Google Analytics, Market Research, Strategic Analysis, Stakeholder Management, Credit Risk Assessment'
};

// ── LETTER TEMPLATES ──
const templates = {
  big4: {
    opener: `I am writing to express my strong interest in the {role} position at {company}. As an MBA student specialising in Finance and Business Analytics at IILM University, Gurugram, with hands-on experience in financial analysis and stakeholder management, I am confident in my ability to contribute meaningfully to {company}'s audit, advisory, or consulting practice.`,
    body1_financial_modeling: `My academic and project work has equipped me with a rigorous foundation in financial modeling, DCF valuation, and three-statement analysis. I have built integrated financial models benchmarked against peer companies using EV/EBITDA multiples — the kind of quantitative discipline that underpins high-quality advisory work at a Big 4 firm. My Excel proficiency (VLOOKUP, Pivot Tables, financial modeling) and Power BI skills enable me to translate complex data into clear, actionable insights for client stakeholders.`,
    body1_business_analytics: `My hands-on experience designing Power BI dashboards and applying analytics frameworks to real-world business problems has sharpened my ability to turn raw data into strategic recommendations. I have worked with CRM data to identify retention gaps and operational inefficiencies — the kind of data-driven problem solving that drives value in Big 4 advisory engagements.`,
    body1_market_research: `Through independent market research projects and my MBA coursework in Business Analytics, I have developed a structured approach to competitive analysis, market sizing, and strategic recommendations — core skills for Big 4 strategy and advisory work. My ability to synthesise qualitative and quantitative data into executive-level deliverables mirrors the high standards expected in professional services.`,
    body1_default: `My experience spans financial sales at HDB Financial Services, independent market research, and academic projects in financial modeling and valuation — giving me a unique combination of analytical rigour and client-facing communication skills that align well with the demands of a Big 4 professional services environment.`,
    body2: `During my tenure at HDB Financial Services Ltd., I managed 20–30+ client interactions weekly, maintained 100% regulatory compliance, and collaborated with cross-functional teams — skills directly transferable to client engagement and project delivery at {company}. My CAT 2024 score of 78 percentile and NMAT score of 227 reflect the analytical sharpness and structured thinking that I bring to every challenge.`,
    closer: `I am deeply aligned with {company}'s commitment to excellence and client impact. I would welcome the opportunity to discuss how my background in finance, analytics, and stakeholder management can contribute to your team. Thank you for considering my application.`
  },

  consulting: {
    opener: `I am writing to apply for the {role} position at {company}. As an MBA student in Finance and Business Analytics with a demonstrated ability to structure complex business problems and deliver data-driven recommendations, I am drawn to {company}'s reputation for tackling the world's most challenging strategic questions.`,
    body1_financial_modeling: `My financial modeling and valuation work — including DCF analysis, scenario modeling, and competitive benchmarking — has trained me to think in frameworks and communicate insights with precision. I approach every problem by first structuring the issue tree, identifying key drivers, and building evidence-based recommendations — consistent with the consulting methodology at {company}.`,
    body1_market_research: `My market entry strategy project for a D2C brand — using Porter's Five Forces, customer segmentation, and phased GTM planning — mirrors the structured problem-solving approach central to consulting engagements. I am comfortable developing hypotheses, designing analyses, and building the narrative arc that translates data into executive recommendations.`,
    body1_default: `I have developed a strong foundation in structured problem-solving through academic case studies, independent market research, and competitive benchmarking projects. I approach problems the way a consultant does — with a clear hypothesis, a structured analytical framework, and a results-oriented mindset.`,
    body2: `My CAT 2024 percentile of 78 and NMAT score of 227 demonstrate the quantitative rigour and logical reasoning that consulting demands. My grassroots experience at Shramik Bharti NGO — engaging 200+ stakeholders across government, community, and NGO levels — gave me rare exposure to navigating complex multi-stakeholder environments, a skill I would bring directly to client projects at {company}.`,
    closer: `I am excited about the possibility of contributing to {company}'s mission of delivering transformational impact. I would love the opportunity to walk you through my project work and discuss how I can add value to your practice. Thank you for your time and consideration.`
  },

  investment: {
    opener: `I am writing to express my keen interest in the {role} opportunity at {company}. With a strong foundation in financial modeling, valuation, and corporate finance — alongside an MBA specialisation in Finance at IILM University — I am eager to contribute to {company}'s deal execution and client advisory capabilities.`,
    body1_financial_modeling: `I have developed hands-on expertise in building three-statement financial models, conducting DCF valuations with WACC and terminal growth assumptions, and running comparable company analyses using EV/EBITDA multiples. I have stress-tested valuations across bull, base, and bear scenarios — producing investment notes structured identically to equity research pitch books. This technical foundation directly supports the rigorous financial analysis required in investment banking.`,
    body1_credit_risk: `My exposure to NBFC lending operations at HDB Financial Services gave me practical understanding of credit risk fundamentals, loan origination funnels, and eligibility assessment — experience that translates directly to the credit analysis and due diligence work central to investment banking.`,
    body1_default: `My academic projects in DCF modeling, portfolio optimisation using Markowitz Mean-Variance theory, and NBFC competitive benchmarking have sharpened my quantitative skills and investment analysis capabilities to the level expected in a demanding investment banking environment.`,
    body2: `My time at HDB Financial Services — where I managed retail financial product sales with full compliance and cross-functional coordination — gave me direct exposure to NBFC operations, client relationship management, and the fundamentals of financial services. This, combined with my CAT 78 percentile and NMAT 227 score, reflects the quantitative aptitude and work ethic required to thrive at {company}.`,
    closer: `I am highly motivated to launch my career in investment banking at {company} and am prepared to commit fully to the demands of the role. I would welcome the chance to discuss my technical background and ambitions in more detail. Thank you for your consideration.`
  },

  tech: {
    opener: `I am writing to apply for the {role} position at {company}. As an MBA student in Finance and Business Analytics with hands-on experience in data analytics, CRM systems, and product management frameworks, I am excited about the opportunity to combine business strategy with technology-driven problem-solving at {company}.`,
    body1_business_analytics: `My experience building Power BI dashboards, working with CRM data, and applying Google Analytics to business problems has given me a strong foundation in data-driven decision-making. I am comfortable working with large datasets, identifying patterns, and communicating insights to non-technical stakeholders — skills that are central to analytical and product roles at leading technology companies.`,
    body1_product_management: `Through my Product Management Insights certification (LinkedIn) and academic projects applying agile frameworks to fintech product design, I have developed a user-centric approach to problem-solving. I am passionate about understanding user needs, defining success metrics, and working cross-functionally to ship impactful products — which aligns strongly with the product culture at {company}.`,
    body1_default: `My combination of financial analytics skills, CRM experience, and product management training gives me a unique lens for approaching technology business problems. I am comfortable operating at the intersection of data, strategy, and user experience — a versatile profile that adds value in fast-moving technology environments.`,
    body2: `As a Google-certified Digital Training Trainer, I have already had direct exposure to the Google ecosystem — training 30+ professionals in digital marketing and analytics under the mentorship of Dr. Sanjay Gathia (Asia Centre × Google). This experience reflects my ability to learn rapidly, communicate complex ideas clearly, and operate within large-scale technology-driven organisations like {company}.`,
    closer: `I am genuinely excited about the work {company} is doing and believe my blend of analytical training, digital certification, and business acumen makes me a strong fit for this role. I would love to discuss how I can contribute to your team. Thank you for considering my application.`
  },

  startup: {
    opener: `I am writing to express my enthusiasm for the {role} role at {company}. As an MBA student with a entrepreneurial mindset, freelance consulting experience, and strong analytical foundations, I am drawn to {company}'s mission and the opportunity to contribute to high-growth, high-impact work in a dynamic environment.`,
    body1_market_research: `My freelance market research work — analysing pricing sensitivity and cost structures for SME clients — has sharpened my ability to generate actionable insights with limited resources and tight timelines. This scrappy, outcome-oriented approach to analysis is exactly what drives value in a startup environment like {company}.`,
    body1_business_analytics: `I have experience translating raw CRM and sales data into actionable dashboards using Power BI and MS Excel, identifying retention gaps, and proposing data-backed growth strategies. In a fast-moving company like {company}, the ability to extract signal from noise quickly is critical — and it's a skill I have consistently demonstrated.`,
    body1_default: `My freelance consulting background, combined with academic training in financial modeling, market research, and product management, has prepared me to operate effectively in ambiguous, resource-constrained environments. I am comfortable wearing multiple hats and moving fast — which is exactly what startup teams need.`,
    body2: `What excites me most about {company} is the opportunity to work on real problems with real business impact from day one. My CAT 78 percentile and NMAT 227 score demonstrate raw analytical ability, while my experience at HDB Financial Services and Shramik Bharti NGO show I can execute under pressure and communicate effectively with diverse stakeholders.`,
    closer: `I am eager to bring my energy, analytical skills, and strategic mindset to {company} and grow with the team. I would love to connect and discuss how I can contribute. Thank you for your time.`
  },

  nbfc: {
    opener: `I am writing to apply for the {role} position at {company}. With direct experience in NBFC retail financial products at HDB Financial Services, combined with my MBA specialisation in Finance and a strong grounding in credit risk and financial analysis, I am well-positioned to contribute to {company}'s lending, analytics, or business development operations.`,
    body1_credit_risk: `During my time at HDB Financial Services Ltd., I gained hands-on exposure to NBFC loan origination, credit eligibility assessment, compliance requirements, and cross-functional coordination between credit, operations, and customer service teams. This real-world grounding in lending processes, combined with my academic training in financial modeling and credit risk analysis, gives me a practical edge for roles within the NBFC and banking sector.`,
    body1_sales_and_crm: `At HDB Financial Services, I managed 20–30+ customer interactions weekly, consistently met conversion targets, and maintained 100% compliance with regulatory requirements. I developed strong expertise in using CRM systems to manage pipelines, track performance metrics, and build lasting client relationships — skills directly applicable to business development and relationship management at {company}.`,
    body1_default: `My combined experience in NBFC operations, financial sales, and academic training in corporate finance and credit risk has given me a comprehensive understanding of the financial services ecosystem — from customer acquisition through to credit assessment and portfolio management.`,
    body2: `My competitive exam performance (CAT 78 percentile, NMAT 227) reflects the quantitative and analytical capability required for rigorous financial analysis roles. Additionally, my MBA coursework in Corporate Finance, combined with project work in NBFC benchmarking and financial modeling, ensures I am technically equipped to contribute immediately at {company}.`,
    closer: `I am genuinely excited about the opportunity to build my career in financial services at {company} and to contribute to your growth objectives. I would welcome the chance to discuss my background in more detail. Thank you for your consideration.`
  },

  fmcg: {
    opener: `I am writing to express my strong interest in the {role} position at {company}. As an MBA student specialising in Finance and Business Analytics, with project experience in FMCG valuation, market entry strategy, and consumer research, I am eager to contribute to {company}'s strategy, analytics, or commercial function.`,
    body1_financial_modeling: `My DCF valuation and three-statement financial modeling project focused specifically on a mid-cap FMCG firm, where I analyzed revenue growth, EBIT margin expansion, and capex schedules — producing an investment thesis benchmarked against sector peers. This deep dive into FMCG financials gave me strong familiarity with the margin dynamics, distribution economics, and competitive positioning challenges that define the sector.`,
    body1_market_research: `My market entry strategy project — evaluating Tier-2 city opportunities for a consumer brand using Porter's Five Forces, customer segmentation, and phased GTM planning — directly mirrors the strategic challenges facing FMCG companies expanding into emerging Indian markets. I bring a structured, data-driven approach to market analysis that translates into clear, executable recommendations.`,
    body1_default: `My academic work in FMCG valuation, consumer market research, and go-to-market strategy has given me a strong understanding of the commercial and financial levers that drive success in the FMCG sector. I am passionate about the intersection of brand strategy, distribution, and financial performance — which is central to the business at {company}.`,
    body2: `My analytical skills — including Advanced Excel, Power BI, and data interpretation — combined with my CAT 78 percentile and NMAT 227 score, reflect the rigor I bring to business problems. My exposure to cross-functional collaboration at HDB Financial Services further prepared me to work effectively in the matrix environments typical of large FMCG organisations like {company}.`,
    closer: `I would be thrilled to bring my passion for consumer strategy and my analytical capabilities to {company}. I would welcome the opportunity to discuss how my background aligns with your team's needs. Thank you very much for your consideration.`
  },

  analytics: {
    opener: `I am writing to apply for the {role} role at {company}. As an MBA student in Business Analytics and Finance with hands-on experience in Power BI, Advanced Excel, and data-driven business research, I am excited about the opportunity to contribute to {company}'s analytics practice.`,
    body1_business_analytics: `My project work includes designing interactive Power BI dashboards that surfaced a 23% customer retention gap from CRM data, building financial models with scenario analysis in Excel, and conducting competitive benchmarking across 12 financial metrics for 5 NBFC firms. I am comfortable working across the full analytics workflow — from data cleaning and modeling to insight communication and stakeholder presentation.`,
    body1_market_research: `As a freelance business researcher, I have applied analytics frameworks to real client problems — mapping pricing sensitivity curves, identifying cost inefficiencies, and translating quantitative findings into actionable SME business recommendations. This practical experience complements my academic training in Business Analytics and Data Interpretation.`,
    body1_default: `My analytics toolkit includes Power BI, Advanced MS Excel (VLOOKUP, Pivot Tables, financial modeling), Google Analytics, and CRM data analysis. I approach analytics problems with a business-first mindset — always asking what decision this data should inform, not just what the numbers say.`,
    body2: `My CAT 2024 score of 78 percentile and NMAT score of 227 demonstrate the quantitative aptitude and logical reasoning that underpins strong analytical work. I am a fast learner who thrives in data-rich environments, and my MBA coursework in Business Analytics and Corporate Finance ensures I can connect analytical outputs to strategic and financial outcomes for clients.`,
    closer: `I am enthusiastic about the opportunity to develop my analytics career at {company} and contribute to delivering high-impact insights for your clients. I would love to discuss my background and project work in more detail. Thank you for your time and consideration.`
  }
};

// ── GENERATE ──
function generateLetter() {
  const company = document.getElementById('companyName').value.trim() || 'your organisation';
  const role = document.getElementById('roleTitle').value.trim() || 'the advertised position';
  const manager = document.getElementById('hiringManager').value.trim();
  const skill = document.getElementById('keySkill').value;
  const extra = document.getElementById('extraNote').value.trim();
  const today = new Date().toLocaleDateString('en-IN', {day:'numeric',month:'long',year:'numeric'});

  const t = templates[selectedType];

  // Pick body paragraph based on skill
  const skillKey = 'body1_' + skill.replace(/ /g,'_').replace(/[^a-z0-9_]/g,'');
  const body1 = (t[skillKey] || t.body1_default)
    .replace(/{company}/g, company)
    .replace(/{role}/g, role);

  const opener = t.opener.replace(/{company}/g, company).replace(/{role}/g, role);
  const body2  = t.body2.replace(/{company}/g, company).replace(/{role}/g, role);
  const closer = t.closer.replace(/{company}/g, company).replace(/{role}/g, role);

  // Tone adjustments
  let salutation = manager ? `Dear ${manager},` : `Dear Hiring Manager,`;
  if(selectedTone === 'enthusiastic') salutation = manager ? `Dear ${manager},` : `Dear Hiring Team,`;

  // Extra note paragraph
  const extraPara = extra ? `\n${extra}\n` : '';

  // Tone modifier for closing
  let closingLine = 'Warm regards,';
  if(selectedTone === 'confident') closingLine = 'With confidence,';
  if(selectedTone === 'enthusiastic') closingLine = 'With great enthusiasm,';
  if(selectedTone === 'concise') closingLine = 'Best regards,';

  const letter = `${today}

${salutation}

${opener}

${body1}

${body2}
${extraPara}
${closer}

${closingLine}

Rudra Pratap Singh
MBA — Finance & Business Analytics | IILM University, Gurugram
📧 rudrapratapsinghchauhan0011@gmail.com
📧 rudrachauhan0011@icloud.com
📞 +91 896-066-9802
🔗 ${profile.linkedin}`;

  // Show with typewriter effect
  currentLetter = letter;
  document.getElementById('emptyState').style.display = 'none';
  const body = document.getElementById('outputBody');
  body.style.display = 'block';
  body.classList.add('typing');
  body.textContent = '';

  let i = 0;
  const speed = 4;
  function type() {
    if(i < letter.length) {
      body.textContent += letter[i++];
      body.scrollTop = body.scrollHeight;
      setTimeout(type, speed);
    } else {
      body.classList.remove('typing');
      updateWordCount(letter);
    }
  }
  type();
}

function updateWordCount(text) {
  const count = text.trim().split(/\s+/).length;
  document.getElementById('wordCount').textContent = count + ' words';
}

async function copyLetter() {
  if(!currentLetter) return;
  await navigator.clipboard.writeText(currentLetter);
  const btn = document.getElementById('copyBtn');
  btn.textContent = '✅ Copied!';
  btn.classList.add('copy-done');
  setTimeout(() => { btn.textContent = '📋 Copy'; btn.classList.remove('copy-done'); }, 2000);
}

function printLetter() {
  if(!currentLetter) return;
  window.print();
}

function downloadLetter() {
  if(!currentLetter) return;
  const company = document.getElementById('companyName').value.trim() || 'Company';
  const role = document.getElementById('roleTitle').value.trim() || 'Role';
  const blob = new Blob([currentLetter], {type:'text/plain'});
  const a = document.createElement('a');
  a.href = URL.createObjectURL(blob);
  a.download = `Cover_Letter_Rudra_${company}_${role}.txt`.replace(/\s+/g,'_');
  a.click();
}
</script>
</body>
</html>
