<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Forcia Natalie SJ Limpiada — Virtual Assistant</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;1,9..144,500&family=Outfit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --cream:#FBF6EF;
    --blush:#F4D9DD;
    --lavender:#E3D9F0;
    --mint:#D7EAE0;
    --gold:#D9A84E;
    --ink:#3B3142;
    --ink-soft:#6E6378;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--cream);
    color:var(--ink);
    font-family:'Outfit', sans-serif;
    line-height:1.6;
    overflow-x:hidden;
  }
  h1,h2,h3{font-family:'Fraunces', serif;}
  a{color:inherit;}
  .wrap{max-width:1080px; margin:0 auto; padding:0 28px;}

  /* subtle blob backdrop */
  .blob{
    position:absolute;
    border-radius:50%;
    filter:blur(40px);
    opacity:.55;
    z-index:0;
  }

  /* NAV */
  nav{
    position:sticky; top:0; z-index:50;
    background:rgba(251,246,239,.85);
    backdrop-filter:blur(8px);
    border-bottom:1px solid rgba(59,49,66,.08);
  }
  nav .wrap{display:flex; align-items:center; justify-content:space-between; padding:16px 28px;}
  .logo{font-family:'Fraunces', serif; font-weight:600; font-size:1.15rem; letter-spacing:.02em;}
  .logo span{color:var(--gold);}
  .navlinks{display:flex; gap:28px; font-size:.92rem; font-weight:500;}
  .navlinks a{text-decoration:none; color:var(--ink-soft); transition:color .2s;}
  .navlinks a:hover{color:var(--ink);}

  /* HERO */
  .hero{
    position:relative;
    padding:90px 0 70px;
    overflow:hidden;
  }
  .hero .blob.b1{width:380px; height:380px; background:var(--blush); top:-120px; right:-80px;}
  .hero .blob.b2{width:260px; height:260px; background:var(--lavender); bottom:-100px; left:-60px;}
  .hero-grid{
    display:grid;
    grid-template-columns:1.2fr .8fr;
    gap:56px;
    align-items:center;
    position:relative;
    z-index:1;
  }
  .eyebrow{
    display:inline-flex; align-items:center; gap:8px;
    font-size:.78rem; letter-spacing:.14em; text-transform:uppercase;
    color:var(--ink-soft); font-weight:600;
    background:var(--mint); padding:6px 14px; border-radius:999px;
    margin-bottom:22px;
  }
  .eyebrow::before{content:"●"; color:var(--gold); font-size:.6rem;}
  h1.title{
    font-size:clamp(2.4rem, 5vw, 3.6rem);
    font-weight:600;
    line-height:1.08;
    margin-bottom:18px;
    letter-spacing:-.01em;
  }
  h1.title em{
    font-style:italic;
    font-weight:400;
    color:var(--gold);
  }
  .subtitle{
    font-size:1.08rem;
    color:var(--ink-soft);
    max-width:480px;
    margin-bottom:30px;
  }
  .cta-row{display:flex; gap:14px; flex-wrap:wrap;}
  .btn{
    display:inline-flex; align-items:center; gap:8px;
    padding:13px 26px;
    border-radius:999px;
    font-weight:600;
    font-size:.92rem;
    text-decoration:none;
    transition:transform .2s, box-shadow .2s;
  }
  .btn-primary{background:var(--ink); color:var(--cream);}
  .btn-primary:hover{transform:translateY(-2px); box-shadow:0 10px 24px rgba(59,49,66,.25);}
  .btn-ghost{border:1.5px solid var(--ink); color:var(--ink);}
  .btn-ghost:hover{background:var(--ink); color:var(--cream);}

  .portrait-card{
    position:relative;
    background:#fff;
    border-radius:28px;
    padding:18px;
    box-shadow:0 30px 60px -20px rgba(59,49,66,.25);
    transform:rotate(-2deg);
  }
  .portrait-card img{
    width:100%; border-radius:20px; display:block; object-fit:cover; aspect-ratio:1/1;
  }
  .portrait-tag{
    position:absolute; bottom:-18px; right:-18px;
    background:var(--gold); color:#fff;
    font-family:'Fraunces', serif; font-weight:600; font-size:.85rem;
    padding:12px 18px; border-radius:16px;
    box-shadow:0 12px 24px rgba(217,168,78,.4);
    transform:rotate(4deg);
  }

  section{padding:70px 0;}
  .section-head{margin-bottom:44px; max-width:640px;}
  .kicker{
    font-size:.78rem; letter-spacing:.14em; text-transform:uppercase;
    color:var(--gold); font-weight:700; margin-bottom:10px;
  }
  .section-head h2{font-size:clamp(1.8rem,3vw,2.4rem); font-weight:600;}

  /* ABOUT */
  .about-grid{display:grid; grid-template-columns:1fr 1fr; gap:48px; align-items:start;}
  .about-grid p{color:var(--ink-soft); margin-bottom:16px;}
  .pill-list{display:flex; flex-wrap:wrap; gap:10px; margin-top:6px;}
  .pill{
    background:var(--lavender);
    padding:8px 16px; border-radius:999px;
    font-size:.85rem; font-weight:500;
  }
  .pill.mint{background:var(--mint);}
  .pill.blush{background:var(--blush);}

  /* SIGNATURE: RECIPE CARD TIMELINE */
  .recipe-section{background:linear-gradient(180deg, var(--cream), #fff 18%, #fff 82%, var(--cream));}
  .recipe-card{
    background:#fff;
    border-radius:24px;
    padding:0;
    box-shadow:0 20px 50px -25px rgba(59,49,66,.2);
    border:1px solid rgba(59,49,66,.06);
    overflow:hidden;
  }
  .recipe-header{
    background:var(--ink);
    color:var(--cream);
    padding:26px 32px;
    display:flex; align-items:center; justify-content:space-between;
    flex-wrap:wrap; gap:10px;
  }
  .recipe-header .rh-title{font-family:'Fraunces', serif; font-size:1.3rem; font-weight:600;}
  .recipe-header .rh-meta{font-size:.8rem; color:var(--blush); letter-spacing:.05em; text-transform:uppercase;}
  .recipe-body{padding:8px 0;}
  .recipe-step{
    display:grid;
    grid-template-columns:64px 1fr;
    padding:26px 32px;
    border-bottom:1px dashed rgba(59,49,66,.12);
    gap:18px;
  }
  .recipe-step:last-child{border-bottom:none;}
  .step-num{
    width:42px; height:42px; border-radius:50%;
    display:flex; align-items:center; justify-content:center;
    font-family:'Fraunces', serif; font-weight:600;
    font-size:.95rem;
    color:#fff;
  }
  .step-num.n1{background:var(--gold);}
  .step-num.n2{background:#C9A2C2;}
  .step-num.n3{background:#8FB9A8;}
  .step-num.n4{background:#A89BD0;}
  .step-num.n5{background:#D98C8C;}
  .step-num.n6{background:#7FA8C9;}
  .step-content .role{font-family:'Fraunces',serif; font-weight:600; font-size:1.08rem; margin-bottom:2px;}
  .step-content .org{color:var(--gold); font-weight:600; font-size:.88rem;}
  .step-content .dates{color:var(--ink-soft); font-size:.8rem; margin-bottom:10px;}
  .step-content ul{list-style:none; color:var(--ink-soft); font-size:.92rem;}
  .step-content ul li{padding-left:18px; position:relative; margin-bottom:4px;}
  .step-content ul li::before{
    content:"•"; position:absolute; left:0; color:var(--gold);
  }

  /* TOOLS */
  .tools-grid{
    display:grid;
    grid-template-columns:repeat(auto-fill,minmax(150px,1fr));
    gap:14px;
  }
  .tool-chip{
    background:#fff;
    border:1px solid rgba(59,49,66,.08);
    border-radius:14px;
    padding:14px 16px;
    font-size:.86rem;
    font-weight:500;
    text-align:center;
    transition:transform .2s, border-color .2s;
  }
  .tool-chip:hover{transform:translateY(-3px); border-color:var(--gold);}

  /* EDUCATION */
  .edu-grid{display:grid; grid-template-columns:1fr 1fr; gap:40px;}
  .edu-card, .seminar-card{
    background:#fff; border-radius:20px; padding:28px;
    border:1px solid rgba(59,49,66,.06);
    box-shadow:0 14px 30px -20px rgba(59,49,66,.18);
  }
  .edu-item{margin-bottom:18px; padding-left:18px; border-left:3px solid var(--mint);}
  .edu-item .yr{font-size:.78rem; color:var(--gold); font-weight:700; letter-spacing:.04em;}
  .edu-item .school{font-weight:600;}
  .seminar-card ul{list-style:none; font-size:.88rem; color:var(--ink-soft);}
  .seminar-card li{padding:7px 0; border-bottom:1px dashed rgba(59,49,66,.1);}
  .seminar-card li:last-child{border-bottom:none;}

  /* CONTACT */
  .contact-section{
    background:var(--ink);
    color:var(--cream);
    border-radius:32px;
    margin:0 28px 70px;
    padding:60px 48px;
    text-align:center;
    position:relative;
    overflow:hidden;
  }
  .contact-section .blob{opacity:.18;}
  .contact-section .blob.c1{width:300px;height:300px;background:var(--blush); top:-80px; left:-60px;}
  .contact-section .blob.c2{width:240px;height:240px;background:var(--mint); bottom:-80px; right:-40px;}
  .contact-section h2{font-size:clamp(1.8rem,3.4vw,2.6rem); margin-bottom:14px; position:relative; z-index:1;}
  .contact-section p{color:#D8CFE0; max-width:480px; margin:0 auto 28px; position:relative; z-index:1;}
  .contact-links{display:flex; gap:16px; justify-content:center; flex-wrap:wrap; position:relative; z-index:1;}
  .contact-links a{
    background:rgba(255,255,255,.08);
    border:1px solid rgba(255,255,255,.2);
    padding:12px 22px; border-radius:999px;
    text-decoration:none; font-size:.9rem; font-weight:500;
    transition:background .2s;
  }
  .contact-links a:hover{background:var(--gold);}

  footer{
    text-align:center; padding:30px 0 50px;
    color:var(--ink-soft); font-size:.82rem;
  }

  @media (max-width: 820px){
    .hero-grid{grid-template-columns:1fr; gap:40px;}
    .hero-grid > div:first-child{order:2;}
    .portrait-card{order:1; max-width:280px; margin:0 auto;}
    .about-grid, .edu-grid{grid-template-columns:1fr;}
    .recipe-step{grid-template-columns:46px 1fr;}
    .contact-section{margin:0 14px 50px; padding:44px 24px;}
  }

  @media (prefers-reduced-motion: reduce){
    *{transition:none !important;}
  }
</style>
</head>
<body>

<nav>
  <div class="wrap">
    <div class="logo">Forcia <span>Limpiada</span></div>
    <div class="navlinks">
      <a href="#about">About</a>
      <a href="#experience">Experience</a>
      <a href="#tools">Tools</a>
      <a href="#education">Education</a>
      <a href="#contact">Contact</a>
    </div>
  </div>
</nav>

<header class="hero">
  <div class="blob b1"></div>
  <div class="blob b2"></div>
  <div class="wrap hero-grid">
    <div>
      <div class="eyebrow">Virtual Assistant &amp; Project Coordinator</div>
      <h1 class="title">Quietly organizing the<br><em>messy parts</em> of your business.</h1>
      <p class="subtitle">I'm Forcia Natalie San Juan-Limpiada — a former Quality Assurance Analyst turned Virtual Assistant. I bring the same precision I used auditing GMP and HACCP standards to calendars, CRMs, launches, and content systems.</p>
      <div class="cta-row">
        <a class="btn btn-primary" href="http://linkedin.com/in/forcia-natalie-san-juan-682a59115/">My LinkedIn</a>
        <a class="btn btn-ghost" href="mailto:chaplimpiada@gmail.com">Email me ↗</a>
      </div>
    </div>
    <div class="portrait-card">
      <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=600&h=600&fit=crop" alt="Portrait placeholder">
      <div class="portrait-tag">6+ yrs<br>remote ops</div>
    </div>
  </div>
</header>

<section id="about">
  <div class="wrap about-grid">
    <div>
      <div class="kicker">About me</div>
      <h2>From the QA lab to the inbox.</h2>
    </div>
    <div>
      <p>I'm a BS Food Technology graduate who spent years auditing production lines before trading lab coats for calendars and CRMs. That background means I notice the small details that keep a process — or a business — running cleanly.</p>
      <p>Outside of work, I'm usually designing in Canva, hunting down new coffee spots, or planning something — work or otherwise. I genuinely enjoy organizing things, which probably explains the career change.</p>
      <div class="pill-list">
        <span class="pill">Adaptable</span>
        <span class="pill mint">Detail-oriented</span>
        <span class="pill blush">Project Manager</span>
        <span class="pill">Multitasking</span>
        <span class="pill mint">Web Design</span>
        <span class="pill blush">Copywriting</span>
      </div>
    </div>
  </div>
</section>

<section id="experience" class="recipe-section">
  <div class="wrap">
    <div class="section-head">
      <div class="kicker">Experience, by the recipe</div>
      <h2>Six roles, one method: prep, support, deliver.</h2>
    </div>
    <div class="recipe-card">
      <div class="recipe-header">
        <div class="rh-title">Career Recipe — serves any growing business</div>
        <div class="rh-meta">Est. 2016 · still simmering</div>
      </div>
      <div class="recipe-body">

        <div class="recipe-step">
          <div class="step-num n1">06</div>
          <div class="step-content">
            <div class="role">Admin Support</div>
            <div class="org">Takeover Marketing · Remote</div>
            <div class="dates">Mauy 2026 – May Present</div>
            <ul><li>Calendar, email, and GoHighLevel Management</li>
            </ul>
          </div>
        </div>

        <div class="recipe-step">
          <div class="step-num n1">06</div>
          <div class="step-content">
            <div class="role">Social Media Manager</div>
            <div class="org">Amazvita · Remote, project-based</div>
            <div class="dates">March 2026 – May 2026</div>
            <ul><li>Manages social media presence and content cadence.</li></ul>
          </div>
        </div>

        <div class="recipe-step">
          <div class="step-num n2">05</div>
          <div class="step-content">
            <div class="role">Project Manager &amp; Multi-role Operator</div>
            <div class="org">Stacey Ishman Coaching · Remote</div>
            <div class="dates">July 2024 – Present</div>
            <ul>
              <li>Calendar, email, and Monday.com automation management.</li>
              <li>Real estate customer support via email/chat.</li>
              <li>Kajabi management, podcast &amp; video editing, website design.</li>
            </ul>
          </div>
        </div>

        <div class="recipe-step">
          <div class="step-num n3">04</div>
          <div class="step-content">
            <div class="role">Podcast &amp; Video Editor</div>
            <div class="org">MoneyFit MD · Remote, project-based</div>
            <div class="dates">January 2026 – March 2026</div>
            <ul><li>Edited podcast episodes and video content end-to-end.</li></ul>
          </div>
        </div>

        <div class="recipe-step">
          <div class="step-num n4">03</div>
          <div class="step-content">
            <div class="role">Executive &amp; Admin Support</div>
            <div class="org">Semi-Retired MD · Remote</div>
            <div class="dates">April 2023 – January 2026</div>
            <ul>
              <li>Calendar/email management, CRM &amp; database upkeep.</li>
              <li>Technical and customer support, email marketing, Kajabi management.</li>
            </ul>
          </div>
        </div>

        <div class="recipe-step">
          <div class="step-num n5">02</div>
          <div class="step-content">
            <div class="role">General VA &amp; Sourcing Specialist</div>
            <div class="org">Various clients · Remote</div>
            <div class="dates">April 2020 – November 2022</div>
            <ul>
              <li>Calendar/email management, B2B ecommerce, transcription.</li>
              <li>CRM and database management; property listing edits (Renthia).</li>
              <li>Website management, SEO, lead generation (Bold Estimation).</li>
            </ul>
          </div>
        </div>

        <div class="recipe-step">
          <div class="step-num n6">01</div>
          <div class="step-content">
            <div class="role">Quality Assurance Analyst / Food Technologist</div>
            <div class="org">Portion Fillers Inc., Bernabest Foodhouse, Cook Asia Inc.</div>
            <div class="dates">2014 – 2020</div>
            <ul>
              <li>GMP &amp; HACCP audits, sensory evaluation, raw material checks.</li>
              <li>Packaging analysis and production documentation.</li>
            </ul>
          </div>
        </div>

      </div>
    </div>
  </div>
</section>

<section id="tools">
  <div class="wrap">
    <div class="section-head">
      <div class="kicker">The toolkit</div>
      <h2>Platforms I work in daily.</h2>
    </div>
    <div class="tools-grid">
      <div class="tool-chip">Kajabi</div>
      <div class="tool-chip">Monday.com</div>
      <div class="tool-chip">Canva</div>
      <div class="tool-chip">ChatGPT / Claude.Ai</div>
      <div class="tool-chip">Zapier</div>
      <div class="tool-chip">Active Campaign</div>
      <div class="tool-chip">ConvertKit</div>
      <div class="tool-chip">Thrive Cart</div>
      <div class="tool-chip">Wordpress / Elementor</div>
      <div class="tool-chip">Adobe Premiere Pro</div>
      <div class="tool-chip">Adobe Photoshop</div>
      <div class="tool-chip">Adobe Lightroom</div>
      <div class="tool-chip">Descript</div>
      <div class="tool-chip">Zendesk</div>
      <div class="tool-chip">Trello</div>
      <div class="tool-chip">Calendly</div>
      <div class="tool-chip">Loom</div>
      <div class="tool-chip">Slack / Discord</div>
      <div class="tool-chip">MS365 / GSuite</div>
      <div class="tool-chip">LinkedIn Sales Navigator</div>
      <div class="tool-chip">Apollo / Dripify</div>
      <div class="tool-chip">Dropbox Sign</div>
      <div class="tool-chip">GoHighLevel</div>
      <div class="tool-chip">Descript</div>
    </div>
  </div>
</section>

<section id="education">
  <div class="wrap">
    <div class="section-head">
      <div class="kicker">Background</div>
      <h2>Education &amp; continued learning.</h2>
    </div>
    <div class="edu-grid">
      <div class="edu-card">
        <h3 style="margin-bottom:18px; font-size:1.1rem;">Education History</h3>
        <div class="edu-item">
          <div class="yr">2010 – 2014</div>
          <div class="school">Laguna State Polytechnic University</div>
          <div style="color:var(--ink-soft); font-size:.88rem;">Los Baños, Laguna — BS Food Technology</div>
        </div>
        <div class="edu-item">
          <div class="yr">2006 – 2010</div>
          <div class="school">Marinduque National High School</div>
          <div style="color:var(--ink-soft); font-size:.88rem;">Boac, Marinduque</div>
        </div>
        <div class="edu-item">
          <div class="yr">2000 – 2006</div>
          <div class="school">Don Luis Hidalgo Memorial School</div>
          <div style="color:var(--ink-soft); font-size:.88rem;">Boac, Marinduque</div>
        </div>
      </div>
      <div class="seminar-card">
        <h3 style="margin-bottom:18px; font-size:1.1rem;">Seminars &amp; Trainings</h3>
        <ul>
          <li>General Virtual Assistance Training (PROVA)</li>
          <li>Facebook Ads Autopilot Course — Kurso.ph</li>
          <li>Social Media Management Course — Kurso.ph</li>
          <li>Graphic Design Canva Course — Kurso.ph</li>
          <li>Wordpress &amp; Marketing Course — Kurso.ph</li>
          <li>Copywriting Course — Kurso.ph</li>
          <li>Packaging Analysis Training — Nestlé Cabuyao Phil.</li>
          <li>UP Pabulum Scientia Sodalitas Symposium — Food Science</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="contact-section">
    <div class="blob c1"></div>
    <div class="blob c2"></div>
    <h2>Let's tidy up your workload.</h2>
    <p>Available for remote VA, project management, Kajabi, and content support work. Reach out by email — it's the fastest way to get a response.</p>
    <div class="contact-links">
      <a href="https://www.linkedin.com/in/forcia-natalie-san-juan-682a59115/">LinkedIn ↗</a>
      <a href="mailto:chaplimpiada@gmail.com">Email Me ↗</a>
    </div>
  </div>
</section>

<footer>
  © 2026 Forcia Natalie SJ Limpiada · References available upon request
</footer>

</body>
</html>
