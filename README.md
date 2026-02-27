<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial
scale=1.0">
  <title>MainCrafts · scrollable service cards</title>
  <!-- Google Fonts + Font Awesome 6 -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?
family=Inter:opsz,wght@14..32,400;14..32,600;14..32,700&display=swap
" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font
awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: 'Inter', sans-serif;
      background: #fbfdff;
      color: #1f2937;
      line-height: 1.5;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }
    main {
      flex: 1;
    }
    :root {
      --primary-light: #4facfe;
      --primary-dark: #00fb54;
      --deep-blue: #0b2b4f;
      --gradient-hero: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
      --card-shadow: 0 20px 30px -10px rgba(0,100,200,0.15);
    }
    /* ----- header / nav ----- */
    header {
      background: rgba(255, 255, 255, 0.92);
      backdrop-filter: blur(10px);
      box-shadow: 0 8px 20px rgba(0,40,80,0.05);
      position: sticky;
      top: 0;
      z-index: 100;
      padding: 0.7rem 2rem;
    }
    nav {
      max-width: 1280px;
      margin: 0 auto;
      display: flex;
align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
    }
    .logo {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 1.9rem;
      font-weight: 700;
      letter-spacing: -0.5px;
    }
    .logo i {
      font-size: 2.3rem;
      background: var(--gradient-hero);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }
    .logo span {
      background: var(--gradient-hero);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }
 nav ul {
      list-style: none;
      display: flex;
      gap: 2.5rem;
      align-items: center;
    }
    nav ul li {
      position: relative;
      padding: 0.6rem 0;
    }
    nav ul li a {
      text-decoration: none;
      font-weight: 600;
      color: #1e293b;
      font-size: 1.1rem;
      transition: color 0.2s;
      display: flex;
      align-items: center;
      gap: 5px;
    }
    nav ul li a i {
      font-size: 0.8rem;
      color: #5f7d9e;
      transition: transform 0.2s;
  }
    nav ul li a:hover {
      color: #b3209a;
    }
    nav ul li:hover > a i {
      transform: rotate(180deg);
      color: #4facfe;
    }
    /* dropdown */
    .dropdown {
      display: none;
      position: absolute;
      top: 100%;
      left: -10px;
      background: white;
      min-width: 210px;
      box-shadow: 0 15px 30px -5px rgba(0,30,60,0.2);
      border-radius: 20px;
      padding: 0.7rem 0;
      border: 1px solid rgba(79, 172, 254, 0.2);
      z-index: 1000;
    }
    .dropdown li {
      width: 100%;
      padding: 0;
   }
    .dropdown li a {
      padding: 0.7rem 1.8rem;
      font-weight: 500;
      color: #2c3e4f;
      transition: all 0.2s;
      gap: 10px;
    }
    .dropdown li a i {
      font-size: 1rem;
      color: #4facfe;
      width: 1.4rem;
      transform: none !important;
    }
    .dropdown li a:hover {
      background: #f0f8ff;
      color: #0b2b4f;
      padding-left: 2.2rem;
    }
    nav ul li:hover .dropdown {
      display: block;
      animation: fadeDrop 0.25s ease;
    }
  @keyframes fadeDrop {
      0% { opacity: 0; transform: translateY(-6px); }
      100% { opacity: 1; transform: translateY(0); }
    }
    nav ul li a.active {
      color: #fe4fa6;
      border-bottom: 3px solid #4facfe;
      padding-bottom: 5px;
    }
    @media (max-width: 700px) {
      nav {
        flex-direction: column;
        gap: 0.5rem;
      }
      nav ul {
        gap: 1.2rem;
        flex-wrap: wrap;
        justify-content: center;
      }
    }
    * ----- footer ----- */
    footer {
      background: #0e2237;
      color: #d2e5ff;
      padding: 2.5rem 2rem 1.8rem;
      margin-top: 3rem;
  }
    .footer-content {
      max-width: 1280px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 1.3rem;
    }
    .footer-links {
      display: flex;
      gap: 2.8rem;
      flex-wrap: wrap;
      justify-content: center;
    }
    .footer-links a {
      color: #bbdbff;
      text-decoration: none;
      font-weight: 500;
      transition: 0.2s;
    }
    .footer-links a:hover {
      color: white;
      transform: translateY(-2px);
 }
    .copyright {
      font-size: 1rem;
      opacity: 0.8;
      border-top: 1px solid #335577;
      padding-top: 1.8rem;
      width: 100%;
      text-align: center;
    }
    /* ----- page header (generic) ----- */
    .page-header {
      background: var(--gradient-hero);
      color: white;
      padding: 4rem 2rem;
      text-align: center;
    }
    .page-header h1 {
      font-size: 3.5rem;
      font-weight: 700;
      letter-spacing: -0.02em;
    }
    .page-header p {
      font-size: 1.3rem;
      max-width: 700px;
      margin: 1rem auto 0;
    }
 .container {
      max-width: 1200px;
      margin: 3rem auto;
      padding: 0 2rem;
    }
    /* ----- HORIZONTAL SCROLL (image cards) for SERVICES ----- */
    .scroll-container {
      max-width: 100%;
      overflow-x: auto;
      overflow-y: hidden;
      padding: 1rem 0.5rem 2rem 0.5rem;
      scroll-behavior: smooth;
      -webkit-overflow-scrolling: touch;
      scrollbar-width: thin;
      scrollbar-color: #4facfe #e0ecff;
    }
    .scroll-container::-webkit-scrollbar {
      height: 10px;
    }
    .scroll-container::-webkit-scrollbar-track {
      background: #e0ecff;
      border-radius: 20px;
    }
    .scroll-container::-webkit-scrollbar-thumb {
      background: linear-gradient(135deg, #4facfe, #00c6fb);
      border-radius: 20px;
  }
    .image-card-row {
      display: flex;
      gap: 2rem;
      width: max-content;
      padding: 0.5rem 1rem;
    }
    .service-image-card {
      width: 320px;
      background: white;
      border-radius: 32px;
      box-shadow: var(--card-shadow);
      overflow: hidden;
      transition: 0.25s ease;
      border: 1px solid rgba(79,172,254,0.2);
      display: flex;
      flex-direction: column;
    }
    .service-image-card:hover {
      transform: translateY(-8px) scale(1.01);
      border-color: #4facfe;
      box-shadow: 0 30px 40px -12px #4facfe;
    }
    .card-img {
   width: 100%;
      height: 200px;
      object-fit: cover;
      display: block;
      background: #d9eaff;
    }
    .card-content {
      padding: 1.8rem 1.5rem 1.8rem;
      text-align: left;
    }
    .card-content h3 {
      font-size: 1.8rem;
      font-weight: 700;
      margin-bottom: 0.75rem;
      background: linear-gradient(145deg, #0b2b4f, #2b5876);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }
    .card-content p {
      color: #3b5e7a;
      margin-bottom: 1.5rem;
      line-height: 1.6;
    }
 .card-tag {
      display: inline-block;
      background: #e2f0ff;
      color: #1e4c7a;
      border-radius: 40px;
      padding: 0.3rem 1rem;
      font-weight: 600;
      font-size: 0.9rem;
    }
    /* ----- other sections (home, features) simple cards (existing style) ----- 
*/
    .cards-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 2.5rem;
    }
    .feature-card {
      background: white;
      border-radius: 32px;
      padding: 2.2rem 1.5rem;
      box-shadow: var(--card-shadow);
      border: 1px solid rgba(79, 172, 254, 0.15);
      transition: 0.3s;
      text-align: center;
    }
    .feature-card i {
      font-size: 3rem;
  background: linear-gradient(145deg, #4facfe, #00d4e0);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      margin-bottom: 1rem;
    }
    .feature-card h3 {
      font-size: 1.8rem;
      margin-bottom: 0.5rem;
      color: #142c44;
    }
    .feature-card p {
      color: #3b5e7a;
    }
    .feature-card:hover {
      transform: translateY(-10px);
      border-color: #4facfe;
      box-shadow: 0 35px 40px -15px #4facfe90;
    }
    /* contact form (unchanged) */
    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 3rem;
 align-items: start;
    }
    .contact-info {
      background: #f4faff;
      padding: 2rem;
      border-radius: 30px;
    }
    .contact-info i {
      color: #4facfe;
      margin-right: 12px;
      width: 2rem;
    }
    .info-line {
      display: flex;
      align-items: center;
      margin: 1.8rem 0;
      font-size: 1.2rem;
    }
    .contact-form input,
    .contact-form textarea {
      width: 100%;
      padding: 15px 20px;
      border: 2px solid #e0ecff;
      border-radius: 40px;
      font-family: 'Inter', sans-serif;
      font-size: 1rem;
      margin-bottom: 1.2rem;
      transition: 0.2s;
   }
    .contact-form input:focus,
    .contact-form textarea:focus {
      border-color: #4facfe;
      outline: none;
    }
    .contact-form button {
      background: var(--gradient-hero);
      border: none;
      color: white;
      font-weight: 700;
      padding: 16px 35px;
      border-radius: 40px;
      font-size: 1.2rem;
      cursor: pointer;
      transition: 0.2s;
    }
    .contact-form button:hover {
      transform: scale(1.02);
      box-shadow: 0 15px 20px -8px #4facfe;
    }
    @media (max-width:700px){
      .contact-grid{grid-template-columns:1fr;}
    }
    hr.divider {
      border: none;
      height: 3px;

         background: linear-gradient(90deg, transparent, #4facfe, 
transparent);
      width: 180px;
      margin: 1rem auto 2rem;
    }
    .btn-primary {
      transition: 0.2s;
      display: inline-block;
    }
    .btn-primary:hover {
      transform: scale(1.05);
      background: #f0f8ff;
    }
    .page-content { padding-bottom: 1rem; }
  </style>
</head>
<body>
<header>
  <nav>
    <div class="logo">
      <i class="fas fa-cubes"></i>
      <span>MainCrafts</span>
    </div>
    <ul>
      <li><a href="?page=home" class="active">Home</a></li>
      <li><a href="?page=features">Features</a></li>
      <!-- services dropdown - now pointing to main services page with 
scroll -->
<li>
        <a href="?page=services">Services <i class="fas fa-chevron
down"></i></a>
        <ul class="dropdown">
          <li><a href="?page=webdesign"><i class="fas fa-laptop
code"></i> Web Design</a></li>
          <li><a href="?page=appdev"><i class="fas fa-mobile-alt"></i> 
App Development</a></li>
          <li><a href="?page=cloud"><i class="fas fa-cloud"></i> Cloud 
Solutions</a></li>
        </ul>
      </li>
      <li><a href="?page=contact">Contact</a></li>
    </ul>
  </nav>
</header>
<main>
  <!-- ############ HOME PAGE ############ -->
  <div id="page-home" class="page-content" style="display: block;">
    <section style="background: var(--gradient-hero); min-height: 85vh; 
display: flex; align-items: center; justify-content: center; text-align: center;
color: white; padding: 2rem;">
      <div>
        <h1 style="font-size: clamp(2.8rem, 12vw, 5rem); font-weight: 
700;">Build Smarter with MainCrafts</h1>
        <p style="font-size: 1.6rem; margin: 1.5rem 0;">Modern stack · 
production-ready</p>
        <a href="?page=contact" class="btn-primary" style="background: 
white; color: #0b2b4f; padding: 16px 45px; border-radius: 50px; font
weight: 700; text-decoration: none; display: inline-block; font-size: 
1.3rem;"><i class="fas fa-rocket"></i> Get Started</a>
      </div>
  </section>
    <section class="container">
      <h2 style="font-size: 2.8rem; text-align: center; background: linear
gradient(145deg,#0b2b4f,#2b5876); -webkit-background-clip: text; 
background-clip: text; color: transparent;">Features that matter</h2>
      <hr class="divider">
      <div class="cards-grid">
        <div class="feature-card"><i class="fas 
fa-tachometer-alt"></i><h3>Fast</h3><p>Optimized for speed, edge 
ready.</p></div>
        <div class="feature-card"><i class="fas 
fa-mobile-alt"></i><h3>Responsive</h3><p>Perfect on any 
device.</p></div>
        <div class="feature-card"><i class="fas 
fa-chart-line"></i><h3>Scalable</h3><p>Grows with your 
ideas.</p></div>
        <div class="feature-card"><i class="fas 
fa-paint-brush"></i><h3>Modern UI</h3><p>Gradients & glass hover 
effects.</p></div>
      </div>
    </section>
  </div>
  <!-- ############ FEATURES SUBPAGE ############ -->
  <div id="page-features" class="page-content" style="display: none;">
    <div class="page-header">
      <h1>Features</h1>
      <p>Everything you need to ship faster</p>
    </div>
    <div class="container">
      <div class="cards-grid">
  <div class="feature-card"><i class="fas 
fa-bolt"></i><h3>Lightning</h3><p>Instant loads, thanks to modern 
stack.</p></div>
        <div class="feature-card"><i class="fas fa-eye"></i><h3>Retina 
ready</h3><p>Sharp design on every screen.</p></div>
        <div class="feature-card"><i class="fas 
fa-cubes"></i><h3>Component based</h3><p>Reusable, maintainable
code.</p></div>
        <div class="feature-card"><i class="fas 
fa-chart-pie"></i><h3>Analytics</h3><p>Built-in conversion 
insights.</p></div>
      </div>
    </div>
  </div>
  <!-- ############ SERVICES main page (with HORIZONTAL 
SCROLLING IMAGE CARDS) ############ -->
  <div id="page-services" class="page-content" style="display: none;">
    <div class="page-header">
      <h1>Our Services</h1>
      <p>scroll → explore image cards</p>
    </div>
    <div class="container" style="max-width: 1400px;">
      <!-- horizontal scroll wrapper -->
      <div class="scroll-container">
        <div class="image-card-row">
          <!-- card 1: Web Design -->
          <div class="service-image-card">
            <!-- image from placeholder (representative) -->
            <img class="card-img" 
src="https://placehold.co/600x400/4facfe/white?text=Web+Design" 
alt="Web design showcase">
            <div class="card-content">
  <h3>Web Design</h3>
              <p>Stunning, responsive websites with modern animations and 
hover effects. Tailored to your brand.</p>
              <span class="card-tag"><i class="far fa-clock"></i> 6 
projects</span>
            </div>
          </div>
          <!-- card 2: App Development -->
          <div class="service-image-card">
            <img class="card-img" 
src="https://placehold.co/600x400/00c6fb/white?text=App+Dev" 
alt="App development">
            <div class="card-content">
              <h3>App Dev</h3>
              <p>Native & cross-platform (Flutter, React Native). iOS and 
Android apps with sleek UI.</p>
              <span class="card-tag"><i class="fas fa-code"></i> 12+ 
apps</span>
            </div>
          </div>
          <!-- card 3: Cloud Solutions -->
          <div class="service-image-card">
            <img class="card-img" 
src="https://placehold.co/600x400/0b2b4f/white?text=Cloud" alt="Cloud 
infrastructure">
            <div class="card-content">
              <h3>Cloud</h3>
              <p>AWS, Azure, Google. Scalable, secure, serverless or 
containerized. 24/7 monitoring.</p>
              <span class="card-tag"><i class="fas fa-database"></i> 
enterprise ready</span>
            </div>
</div>
          <!-- card 4: extra (E-commerce) to show scrolling -->
          <div class="service-image-card">
            <img class="card-img" 
src="https://placehold.co/600x400/4a90e2/white?text=E-commerce" 
alt="E-commerce">
            <div class="card-content">
              <h3>E-commerce</h3>
              <p>Full online stores with payment, inventory, and dashboards. 
Shopify plus custom.</p>
              <span class="card-tag"><i class="fas fa-cart-plus"></i> 20+ 
stores</span>
            </div>
          </div>
          <!-- card 5: AI Solutions -->
          <div class="service-image-card">
            <img class="card-img" 
src="https://placehold.co/600x400/667eea/white?text=AI+%26+ML" 
alt="AI services">
            <div class="card-content">
              <h3>AI & ML</h3>
              <p>Integrate smart features: recommendations, chatbots, 
computer vision.</p>
              <span class="card-tag"><i class="fas fa-robot"></i> 
innovative</span>
            </div>
          </div>
        </div>
      </div>
      <p style="text-align: center; margin-top: 1rem; color: #4f6f8f;"><i 
class="fas fa-arrow-left"></i>  swipe / scroll  <i class="fas fa-arrow
right"></i></p>
 </div>
  </div>
  <!-- ############ SERVICE DETAIL PAGES (also with small scroll, 
but optional) ############ -->
  <div id="page-webdesign" class="page-content" style="display: 
none;">
    <div class="page-header" style="background: linear
gradient(135deg,#667eea,#764ba2);">
      <h1>Web Design</h1>
      <p>beautiful, fast, user-centric</p>
    </div>
    <div class="container" style="text-align: center;">
      <img src="https://placehold.co/800x400/4facfe/white?
text=Web+Design+Showcase" style="width:100%; max-width:800px; 
border-radius:40px; margin:1rem auto; box-shadow: var(--card
shadow);">
      <h2>Custom websites that convert</h2>
      <p style="max-width:700px; margin:2rem auto">We build responsive,
accessible designs with modern animations and hover effects. From 
wireframe to deployment.</p>
      <a href="?page=contact" class="btn-primary" 
style="background:var(--gradient-hero); color:white; padding:12px 30px; 
border-radius:40px; text-decoration:none;">start a project</a>
    </div>
  </div>
  <div id="page-appdev" class="page-content" style="display: none;">
    <div class="page-header" style="background: linear
gradient(135deg,#11998e,#38ef7d);">
      <h1>App Development</h1>
      <p>native + cross platform</p>
    </div>
   <div class="container" style="text-align: center;">
      <img src="https://placehold.co/800x400/00d4a0/white?
text=Mobile+Apps" style="width:100%; max-width:800px; border
radius:40px; margin:1rem auto; box-shadow: var(--card-shadow);">
      <h2>iOS · Android · Flutter · React Native</h2>
      <p>Fast, secure and scalable mobile experiences.</p>
    </div>
  </div>
  <div id="page-cloud" class="page-content" style="display: none;">
    <div class="page-header" style="background: linear
gradient(135deg,#3a1c71,#d76d77,#ffaf7b);">
      <h1>Cloud Solutions</h1>
      <p>infrastructure that grows</p>
    </div>
    <div class="container" style="text-align: center;">
      <img src="https://placehold.co/800x400/0b2b4f/white?
text=Cloud+Infra" style="width:100%; max-width:800px; border
radius:40px; margin:1rem auto; box-shadow: var(--card-shadow);">
      <h2>AWS, Google Cloud, Azure</h2>
      <p>Scalable architecture, serverless, containers and more.</p>
    </div>
  </div>
  <!-- ############ CONTACT PAGE ############ -->
  <div id="page-contact" class="page-content" style="display: none;">
    <div class="page-header" style="background: var(--gradient-hero);">
      <h1>Contact us</h1>
      <p>We reply within 24h</p>
    </div>
 <div class="container contact-grid">
      <div class="contact-info">
        <div class="info-line"><i class="fas fa-map-marker-alt"></i> San 
Francisco, CA</div>
        <div class="info-line"><i class="fas fa-phone"></i> +1 (555) 724
6832</div>
        <div class="info-line"><i class="fas fa-envelope"></i> 
hello@maincrafts.tech</div>
        <div style="margin-top: 2rem;">
          <i class="fab fa-twitter" style="font-size:2rem; margin
right:15px;"></i>
          <i class="fab fa-github" style="font-size:2rem; margin
right:15px;"></i>
          <i class="fab fa-linkedin" style="font-size:2rem;"></i>
        </div>
      </div>
      <div class="contact-form">
        <form>
          <input type="text" placeholder="Your name">
          <input type="email" placeholder="Email address">
          <textarea rows="4" placeholder="How can we help?"></textarea>
          <button type="submit"><i class="fas fa-paper-plane"></i> Send 
message</button>
        </form>
      </div>
    </div>
  </div>
</main>
<footer>
  <div class="footer-content">
  <div class="footer-links">
      <a href="?page=home">Privacy Policy</a>
      <a href="?page=home">Terms</a>
      <a href="?page=contact">Contact</a>
    </div>
    <div class="copyright">
      <i class="far fa-copyright"></i> 2025 MainCrafts Technology. All 
rights reserved.
    </div>
  </div>
</footer>
<!-- Client-side routing (same as before) -->
<script>
  (function() {
    const pages = ['home', 'features', 'services', 'webdesign', 'appdev', 
'cloud', 'contact'];
    function showPage(pageId) {
      document.querySelectorAll('.page-content').forEach(el => 
el.style.display = 'none');
      const target = document.getElementById('page-' + pageId);
      if (target) target.style.display = 'block';
      else document.getElementById('page-home').style.display = 'block';
      document.querySelectorAll('nav ul li a').forEach(link => {
        link.classList.remove('active');
        const href = link.getAttribute('href') || '';
        if (href === '?page=' + pageId || (pageId === 'home' && href === 
'?page=home')) {
  link.classList.add('active');
        }
        if (pageId === 'services' && link.getAttribute('href') === '?
page=services') link.classList.add('active');
      });
    }
    const urlParams = new URLSearchParams(window.location.search);
    let currentPage = urlParams.get('page') || 'home';
    if (!pages.includes(currentPage)) currentPage = 'home';
    showPage(currentPage);
    document.addEventListener('click', function(e) {
      const link = e.target.closest('a');
      if (!link) return;
      const href = link.getAttribute('href') || '';
      if (href.startsWith('?page=')) {
        e.preventDefault();
        const page = href.replace('?page=', '');
        if (pages.includes(page)) {
          const url = new URL(window.location);
          url.searchParams.set('page', page);
          window.history.pushState({}, '', url);
          showPage(page);
        } else {
          window.location.href = href;
        }
      }
    });
 window.addEventListener('popstate', function() {
 const params = new URLSearchParams(window.location.search);
 const page = params.get('page') || 'home';
 showPage(page);
 });
 })();
</script>
</body>
</html>

