<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Main menu</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">

<link rel="stylesheet"
href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css"/>

<style>

:root{
    --bg:#081120;
    --card:#0f172a;
    --card2:#13203a;
    --primary:#00e5ff;
    --secondary:#6366f1;
    --text:#f8fafc;
    --muted:#94a3b8;
    --border:rgba(255,255,255,.08);
}

/* =========================
RESET
========================= */

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:'Inter',sans-serif;
    background:linear-gradient(180deg,#050b16,#081120,#0b1728);
    color:var(--text);
    min-height:200vh;
    overflow-x:hidden;
}

/* =========================
DEMO CONTENT
========================= */

.demo-section{
    padding:140px 7% 120px;
    text-align:center;
}

.demo-badge{
    display:inline-flex;
    align-items:center;
    gap:10px;
    padding:12px 20px;
    border-radius:999px;
    background:rgba(0,229,255,.08);
    border:1px solid rgba(0,229,255,.15);
    color:#a5f3fc;
    margin-bottom:25px;
    font-size:.85rem;
}

.demo-section h1{
    font-size:clamp(2.8rem,8vw,5rem);
    line-height:1.05;
    margin-bottom:24px;
    font-weight:900;
}

.demo-section h1 span{
    background:linear-gradient(90deg,var(--primary),#818cf8);
    -webkit-background-clip:text;
    -webkit-text-fill-color:transparent;
}

.demo-section p{
    max-width:760px;
    margin:auto;
    color:var(--muted);
    line-height:1.9;
    font-size:1.05rem;
}

/* =========================
TRIGGER BUTTON
========================= */

.sidebar-trigger{
    position:fixed;
    top:25px;
    right:25px;
    width:20px;
    height:20px;
    border:none;
    border-radius:24px;
    background:linear-gradient(135deg,var(--primary),var(--secondary));
    color:#00111a;
    font-size:1.6rem;
    cursor:pointer;
    z-index:99999;
    box-shadow:0 20px 45px rgba(0,229,255,.3);
    transition:.35s ease;
    animation:heartbeat 4s infinite;
}

.sidebar-trigger:hover{
    transform:translateY(-5px) scale(1.04);
}

@keyframes heartbeat{
    0%{transform:scale(1);}
    10%{transform:scale(1.08);}
    20%{transform:scale(1);}
    30%{transform:scale(1.08);}
    40%{transform:scale(1);}
}

/* =========================
OVERLAY
========================= */

.sidebar-overlay{
    position:fixed;
    inset:0;
    background:rgba(3,8,18,.92);
    backdrop-filter:blur(20px);
    z-index:99998;
    display:flex;
    justify-content:flex-end;
    opacity:0;
    visibility:hidden;
    transition:.45s ease;
}

.sidebar-overlay.active{
    opacity:1;
    visibility:visible;
}

/* =========================
SIDEBAR PANEL
========================= */

.sidebar-panel{
    width:min(92%,420px);
    height:90%;
    background:linear-gradient(180deg,#0f172a,#111c33);
    border-left:1px solid rgba(255,255,255,.08);
    padding:30px;
    overflow-y:auto;
    transform:translateX(100%);
    transition:.45s ease;
    position:relative;
}

.sidebar-overlay.active .sidebar-panel{
    transform:translateX(0);
}

/* =========================
HEADER
========================= */

.sidebar-header{
    display:flex;
    align-items:center;
    justify-content:space-between;
    margin-bottom:35px;
}

.logo{
    display:flex;
    align-items:center;
    gap:14px;
}

.logo-icon{
    width:52px;
    height:52px;
    border-radius:18px;
    background:linear-gradient(135deg,var(--primary),var(--secondary));
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:1.3rem;
    color:#00111a;
}

.logo h2{
    font-size:1rem;
    font-weight:800;
}

.logo p{
    color:var(--muted);
    font-size:.75rem;
}

.close-btn{
    width:44px;
    height:44px;
    border:none;
    border-radius:14px;
    background:rgba(255,255,255,.06);
    color:white;
    cursor:pointer;
    font-size:1rem;
}

/* =========================
INFO CARD
========================= */

.info-card{
    background:rgba(255,255,255,.03);
    border:1px solid rgba(255,255,255,.06);
    border-radius:26px;
    padding:24px;
    margin-bottom:30px;
}

.info-card h3{
    font-size:1.2rem;
    margin-bottom:12px;
}

.info-card p{
    color:var(--muted);
    line-height:1.8;
    font-size:.95rem;
}

/* =========================
MENU LIST
========================= */

.menu-list{
    display:flex;
    flex-direction:column;
    gap:18px;
}

.menu-item{
    display:flex;
    align-items:center;
    gap:18px;
    padding:20px;
    border-radius:24px;
    text-decoration:none;
    color:white;
    background:rgba(255,255,255,.03);
    border:1px solid rgba(255,255,255,.05);
    transition:.35s ease;
    opacity:0;
    transform:translateX(20px);
}

.sidebar-overlay.active .menu-item{
    opacity:1;
    transform:translateX(0);
}

.menu-item:nth-child(1){transition-delay:.1s;}
.menu-item:nth-child(2){transition-delay:.18s;}
.menu-item:nth-child(3){transition-delay:.26s;}
.menu-item:nth-child(4){transition-delay:.34s;}
.menu-item:nth-child(5){transition-delay:.42s;}

.menu-item:hover{
    transform:translateY(-5px);
    border-color:rgba(0,229,255,.22);
    background:rgba(0,229,255,.05);
}

.menu-icon{
    min-width:42px;
    height:42px;
    border-radius:20px;
    background:linear-gradient(135deg,var(--primary),#818cf8);
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:1.3rem;
    color:#00111a;
}

.menu-text h4{
    font-size:1rem;
    margin-bottom:6px;
}

.menu-text p{
    color:var(--muted);
    font-size:.86rem;
    line-height:1.7;
}

/* =========================
SUGGESTIONS
========================= */

.suggestions{
    margin-top:40px;
}

.suggestions h3{
    margin-bottom:20px;
    font-size:1.1rem;
}

.suggestion-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:15px;
}

.suggestion-card{
    background:rgba(255,255,255,.03);
    border:1px solid rgba(255,255,255,.06);
    border-radius:22px;
    padding:20px;
}

.suggestion-card i{
    font-size:1.5rem;
    margin-bottom:16px;
    color:#67e8f9;
}

.suggestion-card h4{
    margin-bottom:10px;
}

.suggestion-card p{
    color:var(--muted);
    line-height:1.7;
    font-size:.85rem;
}

/* =========================
SLOW POPUP
========================= */

.slow-popup{
    position:fixed;
    left:50%;
    bottom:110px;
    transform:translateX(-50%);
    width:min(92%,420px);
    background:rgba(15,23,42,.95);
    border:1px solid rgba(255,255,255,.08);
    border-radius:28px;
    padding:24px;
    z-index:99997;
    opacity:0;
    visibility:hidden;
    transition:1s ease;
    box-shadow:0 20px 60px rgba(0,0,0,.4);
}

.slow-popup.active{
    opacity:1;
    visibility:visible;
    bottom:130px;
}

.slow-popup h3{
    margin-bottom:10px;
}

.slow-popup p{
    color:var(--muted);
    line-height:1.8;
    margin-bottom:18px;
}

.popup-btn{
    width:100%;
    border:none;
    padding:15px;
    border-radius:16px;
    background:linear-gradient(135deg,var(--primary),var(--secondary));
    color:#00111a;
    font-weight:800;
    cursor:pointer;
}

/* =========================
MOBILE
========================= */

@media(max-width:768px){

.sidebar-trigger{
    width:44px;
    height:44px;
    right:18px;
    bottom:18px;
}

.sidebar-panel{
    width:100%;
}

.suggestion-grid{
    grid-template-columns:1fr;
}

}

</style>
</head>

<body>

<!-- DEMO CONTENT -->
<section class="demo-section">

    <div class="demo-badge">
        <i class="fas fa-bolt"></i>
        Reusable GitHub Widget
    </div>

    <h1>
        Modern Sidebar
        <span>Overlay System</span>
    </h1>

    <p>
        Professional floating sidebar trigger optimized for GitHub Pages,
        personal portfolios, AI startups, blogging hubs,
        affiliate stores, digital products, and reusable widget systems.
    </p>

</section>

<!-- SIDEBAR TRIGGER -->
<button class="sidebar-trigger"
onclick="toggleSidebar()">

    <i class="fas fa-layer-group"></i>

</button>

<!-- OVERLAY -->
<div class="sidebar-overlay"
id="sidebarOverlay">

    <!-- SIDEBAR -->
    <div class="sidebar-panel">

        <!-- HEADER -->
        <div class="sidebar-header">

            <div class="logo">

                <div class="logo-icon">
                    <i class="fas fa-robot"></i>
                </div>

                <div>
                    <h2>links Hub</h2>
                    <p>Premium Navigation Overlay</p>
                </div>

            </div>

            <button class="close-btn"
            onclick="toggleSidebar()">

                <i class="fas fa-times"></i>

            </button>

        </div>

        <!-- INFO -->
        <div class="info-card">

            <h3>
                Explore Digital Ecosystem
            </h3>

            <p>
                Open premium pages, starter kits,
                blog resources, portfolio systems,
                and reusable GitHub experiences.
            </p>

        </div>

        <!-- MENU -->
        <div class="menu-list">

            <!-- BLOGs -->
            <a class="menu-item"
            href="https://debeatzgh1.github.io/blogs"
            target="_blank"
            loading="lazy">

                <div class="menu-icon">
                    <i class="fas fa-blog"></i>
                </div>

                <div class="menu-text">
                    <h4>Blog</h4>
                    <p>
                        AI articles, blogging resources,
                        side hustles, and digital growth content.
                    </p>
                </div>

            </a>

            <!-- HOME -->
            <a class="menu-item"
            href="https://debeatzgh1.github.io/Home-/"
            target="_blank">

                <div class="menu-icon">
                    <i class="fas fa-house"></i>
                </div>

                <div class="menu-text">
                    <h4>Home Page</h4>
                    <p>
                        Main ecosystem dashboard
                        with projects, links, and premium resources.
                    </p>
                </div>

            </a>

            <!-- Postfeed -->
            <a class="menu-item"
            href="https://debeatzgh1.github.io/posts/"
            target="_blank">

                <div class="menu-icon">
                    <i class="fas fa-layer-group"></i>
                </div>

                <div class="menu-text">
                    <h4>Pages</h4>
                    <p>
                        Explore curated GitHub pages,
                        modern UI layouts, and creator systems.
                    </p>
                </div>

            </a>

            <!-- STARTER KITS -->
            <a class="menu-item"
            href="https://debeatzgh1.github.io/TechAdapt-Solutions-Strategies-for-Modern-Startups-and-Individuals/"
            target="_blank">

                <div class="menu-icon">
                    <i class="fas fa-box-open"></i>
                </div>

                <div class="menu-text">
                    <h4>Starter Kits</h4>
                    <p>
                        AI starter kits, productivity systems,
                        and beginner digital resources.
                    </p>
                </div>

            </a>

            <!-- SUGGESTED -->
            <a class="menu-item"
            href="https://debeatzgh1.github.io/firebase-front-end-components/"
            target="_blank">

                <div class="menu-icon">
                    <i class="fas fa-lightbulb"></i>
                </div>

                <div class="menu-text">
                    <h4>Suggested</h4>
                    <p>
                        Recommended side hustle guides,
                        online income systems, and AI business ideas.
                    </p>
                </div>

            </a>

        </div>

        <!-- SUGGESTIONS -->
        <div class="suggestions">

            <h3>
                Featured Widgets
            </h3>

            <div class="suggestion-grid">

                <div class="suggestion-card">

                    <i class="fas fa-code"></i>

                    <h4>Reusable Components</h4>

                    <p>
                        Build scalable UI systems
                        for GitHub and Blogger integration.
                    </p>

                </div>

                <div class="suggestion-card">

                    <i class="fas fa-wand-magic-sparkles"></i>

                    <h4>AI Interfaces</h4>

                    <p>
                        Modern AI layouts,
                        overlays, and chatbot experiences.
                    </p>

                </div>

            </div>

        </div>

    </div>

</div>

<!-- SLOW POPUP -->
<div class="slow-popup"
id="slowPopup">

    <h3>
        Welcome to premium links hub
    </h3>

    <p>
        Open the floating sidebar to explore
        premium GitHub pages, AI starter kits,
        blog resources, and reusable widgets.
    </p>

    <button class="popup-btn"
    onclick="toggleSidebar()">

        Open Sidebar Menu

    </button>

</div>

<script>

/* =========================
TOGGLE SIDEBAR
========================= */

function toggleSidebar(){

    document
    .getElementById('sidebarOverlay')
    .classList
    .toggle('active');

}

/* =========================
CLOSE WHEN OUTSIDE CLICK
========================= */

document
.getElementById('sidebarOverlay')
.addEventListener('click',function(e){

    if(e.target === this){

        this.classList.remove('active');

    }

});

/* =========================
SLOW POPUP
========================= */

setTimeout(()=>{

    document
    .getElementById('slowPopup')
    .classList
    .add('active');

},5000);

/* =========================
REMOVE POPUP AFTER OPEN
========================= */

document
.querySelector('.popup-btn')
.addEventListener('click',()=>{

    document
    .getElementById('slowPopup')
    .classList
    .remove('active');

});

/* =========================
LAZY LOAD EFFECT
========================= */

const observer=new IntersectionObserver((entries)=>{

    entries.forEach(entry=>{

        if(entry.isIntersecting){

            entry.target.style.opacity='1';
            entry.target.style.transform='translateY(0)';

        }

    });

});

document.querySelectorAll('.suggestion-card').forEach(card=>{

    card.style.opacity='0';
    card.style.transform='translateY(20px)';
    card.style.transition='1s ease';

    observer.observe(card);

});

</script>

</body>
</html>

**Curated Guides for Online Business & AI Product Creation**

---

# 🚀 Curated Guides for Online Business & AI Product Creation

Welcome to your go-to resource hub for building, scaling, and optimizing online businesses and digital products with AI. Browse actionable guides, get the latest updates, and start your journey with easy, user-friendly navigation.

---

## 📚 Featured Articles & Guides

---

<table>
  <tr>
    <td>
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/07/17537340755285823677200936422321.jpg" width="160" style="border-radius:12px"/>
      <h3>Learn About Online Business</h3>
      <p>Unlock the basics of online entrepreneurship. Discover step-by-step methods to start blogging and find your digital niche toward success.</p>
      <a href="https://debeatzgh1.blogspot.com/p/start-blogging-on-debeatzgh.html" style="background:#2b7cff;color:#fff;border-radius:6px;padding:12px 28px;font-size:1em;text-decoration:none;display:inline-block;margin-top:10px;font-weight:600;">Learn More</a>
    </td>
    <td>
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/07/17537340887913975074031292849662.jpg" width="160" style="border-radius:12px"/>
      <h3>Online Business Updates</h3>
      <p>Stay current with internet marketing trends and earning opportunities. Regular updates provide fresh insights for your online career.</p>
      <a href="https://debeatzgh1.blogspot.com/p/earn-money-with-internet-marketing.html" style="background:#00b894;color:#fff;border-radius:6px;padding:12px 28px;font-size:1em;text-decoration:none;display:inline-block;margin-top:10px;font-weight:600;">See Updates</a>
    </td>
  </tr>
  <tr>
    <td>
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/09/asleekandmoderngoogleclassroombannerfortechaihubfeaturingfuturisticdigitalelements261807892942313727.jpg" width="160" style="border-radius:12px"/>
      <h3>Ultimate Guide to AI Prompt</h3>
      <p>A comprehensive walkthrough for mastering AI prompts—ideal for content creators, marketers, and digital entrepreneurs wanting smarter outputs and automation.</p>
      <a href="https://debeatzgh1.blogspot.com/2025/06/the-ultimate-guide-to-ai-prompts-for.html" style="background:#fdcb6e;color:#222;border-radius:6px;padding:12px 28px;font-size:1em;text-decoration:none;display:inline-block;margin-top:10px;font-weight:600;">Get the Guide</a>
    </td>
    <td>
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/07/17537330556162704960749447510384.jpg" width="160" style="border-radius:12px"/>
      <h3>How to Build Digital Products Using AI</h3>
      <p>Step-by-step instructions, actionable frameworks, and resources for creating, launching, and selling digital products powered by artificial intelligence.</p>
      <a href="https://debeatzgh1.blogspot.com/p/step-by-step-guide-how-to-build-digital.html" style="background:#6c5ce7;color:#fff;border-radius:6px;padding:12px 28px;font-size:1em;text-decoration:none;display:inline-block;margin-top:10px;font-weight:600;">Start Building</a>
    </td>
  </tr>
  <tr>
    <td>
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/07/screenshot_20250715-094141_13250821742613334585.png" width="160" style="border-radius:12px"/>
      <h3>Online Business Guide</h3>
      <p>An easy-to-follow guide for creating a structured, profitable online business. Find models, checklists, and strategies for sustainable growth.</p>
      <a href="https://debeatzgh1.blogspot.com/p/online-business-guide.html" style="background:#00cec9;color:#222;border-radius:6px;padding:12px 28px;font-size:1em;text-decoration:none;display:inline-block;margin-top:10px;font-weight:600;">Open Guide</a>
    </td>
    <td>
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/07/1753733926370_16223804364286435440.jpg" width="160" style="border-radius:12px"/>
      <h3>Ultimate Guide to Online Business</h3>
      <p>Your go-to resource for launching and scaling any online business, filled with expert insights, proven tactics, and industry secrets.</p>
      <a href="https://debeatzgh1.blogspot.com/p/home.html" style="background:#fab1a0;color:#222;border-radius:6px;padding:12px 28px;font-size:1em;text-decoration:none;display:inline-block;margin-top:10px;font-weight:600;">View Ultimate Guide</a>
    </td>
  </tr>
  <tr>
    <td>
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/11/1761391318708_15855974686444559481.jpg" width="160" style="border-radius:12px"/>
      <h3>How to Start Online Business</h3>
      <p>Begin your digital entrepreneurship with zero experience. Follow this success-oriented guide to business setup and early wins.</p>
      <a href="https://debeatzgh1.blogspot.com/p/business-guide-get-free-successful.html" style="background:#636e72;color:#fff;border-radius:6px;padding:12px 28px;font-size:1em;text-decoration:none;display:inline-block;margin-top:10px;font-weight:600;">Get Started</a>
    </td>
  </tr>
</table>

---

## How to Use This Repo

- **Click the Colored Buttons** to instantly access guides (same tab navigation for focus).
- **Each Thumbnail** preview is optimized for a clean, professional look on any device.
- **Browse & Learn**: Whether a beginner or advanced user, these guides are built to help every step of your online business or AI product journey.

---

**Created with 💡 by [debeatzgh1](https://github.com/debeatzgh1) — Your gateway to digital entrepreneurship and AI-powered growth.**


<style>
/* --- 1. COMMAND CONTROLS (Top-Left) --- */
.modal-controls {
  position: fixed;
  top: 15px;
  left: 15px; /* Moved to top-left as requested */
  display: flex;
  flex-direction: row;
  gap: 12px;
  z-index: 10001;
  background: rgba(15, 15, 20, 0.8);
  padding: 8px;
  border-radius: 12px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(0, 242, 255, 0.3);
  display: none; /* Only visible when Iframe is open */
}

.modal-btn {
  background: transparent;
  color: #00f2ff;
  border: 1px solid rgba(0, 242, 255, 0.2);
  width: 35px;
  height: 35px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: 0.3s;
}

.modal-btn:hover {
  background: #00f2ff;
  color: #000;
  box-shadow: 0 0 15px rgba(0, 242, 255, 0.5);
}

/* --- 2. THIN NAVIGATION INDICATORS --- */
.nav-indicators {
  position: fixed;
  right: 25px;
  top: 50%;
  transform: translateY(-50%);
  display: flex;
  flex-direction: column;
  gap: 20px;
  z-index: 9000;
}

.nav-arrow {
  font-size: 12px;
  color: rgba(255, 255, 255, 0.2);
  transition: 0.5s;
  text-align: center;
}

.nav-arrow.active {
  color: #00f2ff;
  text-shadow: 0 0 10px #00f2ff;
  transform: scale(1.3);
}

/* --- 3. PREMIUM IFRAME CONTAINER --- */
#iframeModal {
  position: fixed;
  inset: 0;
  background: rgba(5, 5, 7, 0.95);
  z-index: 10000;
  display: none;
  padding: 40px 15px 15px 15px; /* Extra top padding for controls */
}

.iframe-wrapper {
  width: 100%;
  height: 100%;
  border-radius: 20px;
  border: 2px solid #00f2ff;
  overflow: hidden;
  box-shadow: 0 0 40px rgba(0, 242, 255, 0.15);
  background: #fff;
}

#iframeModal iframe {
  width: 100%;
  height: 100%;
  border: none;
}

/* ❤️ Heartbeat animation for Floating Dock */
@keyframes heartbeat {
  0% { transform: scale(1); }
  15% { transform: scale(1.1); }
  30% { transform: scale(1); }
}

.floating-btn {
  animation: heartbeat 1.5s ease-in-out infinite;
}
</style>

<div class="container" style="max-width:900px; margin:auto; padding:20px; color:#fff; background:#0f172a; font-family:sans-serif;">
  <h1 style="text-align:center;">🚀 Curated Guides for Online Business</h1>
  
  <div class="nav-indicators">
    <div id="arrow-up" class="nav-arrow"><i class="fas fa-chevron-up"></i><br>UP</div>
    <div id="arrow-down" class="nav-arrow">DOWN<br><i class="fas fa-chevron-down"></i></div>
  </div>

  <table width="100%" style="border-collapse: separate; border-spacing: 0 20px;">
    </table>
</div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  // 1. Setup Iframe & Controls
  const modal = document.createElement("div");
  modal.id = "iframeModal";
  const wrapper = document.createElement("div");
  wrapper.className = "iframe-wrapper";
  const iframe = document.createElement("iframe");
  wrapper.appendChild(iframe);
  modal.appendChild(wrapper);

  const controls = document.createElement("div");
  controls.className = "modal-controls";
  controls.innerHTML = `
    <button class="modal-btn" onclick="closeM()"><i class="fas fa-times"></i></button>
    <button class="modal-btn" onclick="toggleFS()"><i class="fas fa-expand"></i></button>
  `;

  document.body.appendChild(modal);
  document.body.appendChild(controls);

  window.closeM = () => {
    modal.style.display = "none";
    controls.style.display = "none";
    iframe.src = "";
  };

  window.toggleFS = () => {
    if (!document.fullscreenElement) {
      wrapper.requestFullscreen();
    } else {
      document.exitFullscreen();
    }
  };

  // 2. Link Interception (Open in Iframe)
  document.querySelectorAll('a[href*="blogspot.com"]').forEach(link => {
    link.onclick = (e) => {
      e.preventDefault();
      iframe.src = link.href;
      modal.style.display = "block";
      controls.style.display = "flex";
    };
  });

  // 3. Auto-Slide Indicators (Every 3 Seconds)
  const up = document.getElementById('arrow-up');
  const down = document.getElementById('arrow-down');
  let step = 0;

  setInterval(() => {
    if (step === 0) {
      up.classList.add('active');
      down.classList.remove('active');
      step = 1;
    } else {
      down.classList.add('active');
      up.classList.remove('active');
      step = 0;
    }
  }, 3000);

  // 4. Floating Dock (Bottom Center)
  const dock = document.createElement("div");
  Object.assign(dock.style, {
    position: "fixed", bottom: "20px", left: "50%", transform: "translateX(-50%)",
    display: "flex", gap: "10px", zIndex: "9999", padding: "10px",
    background: "rgba(0,0,0,0.5)", borderRadius: "50px", backdropFilter: "blur(10px)"
  });

  const btnData = [
    { text: "Guides", url: "https://debeatzgh1.github.io/Home-/", color: "#2b7cff" },
    { text: "Docs", url: "https://debeatzgh1.github.io/-Floating-Dock-Smart-Iframe-Modal/", color: "#00b894" }
  ];

  btnData.forEach(data => {
    const btn = document.createElement("button");
    btn.innerText = data.text;
    btn.className = "floating-btn";
    Object.assign(btn.style, {
      padding: "8px 20px", borderRadius: "20px", border: "none", color: "#fff",
      background: data.color, cursor: "pointer", fontWeight: "bold", fontSize: "12px"
    });
    btn.onclick = () => {
      iframe.src = data.url;
      modal.style.display = "block";
      controls.style.display = "flex";
    };
    dock.appendChild(btn);
  });
  document.body.appendChild(dock);
});
</script>
