[Beranda.html](https://github.com/user-attachments/files/22750178/Beranda.html)
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>LAYANAN VPN BUNNY — Solusi VPN Perusahaan</title>
  <meta name="description" content="LAYANAN VPN BUNNY — Solusi koneksi aman, terenkripsi, dan andal untuk bisnis. Lindungi data perusahaan, percepat kerja jarak jauh, dan tingkatkan keamanan jaringan." />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#05060a; /* hitam sangat pekat */
      --surface:#0b1220; /* biru gelap */
      --muted:#99a3b3;
      --accent:#0ea5ff; /* biru cerah */
      --accent-2:#2563eb; /* deep blue */
      --card:#0f1724;
      --glass: rgba(255,255,255,0.03);
      --radius:14px;
      --maxw:1100px;
      --white-min: #ffffff;
      font-family: Inter, system-ui, -apple-system, 'Segoe UI', Roboto, Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,var(--bg),#071028);color:#e6eef8;-webkit-font-smoothing:antialiased;}
    a{color:inherit;text-decoration:none}
    .container{max-width:var(--maxw);margin:0 auto;padding:28px}

    /* Loading (putih minimal) */
    #loading{position:fixed;inset:0;background:#ffffff;display:flex;flex-direction:column;align-items:center;justify-content:center;z-index:9999}
    .load-mark{font-weight:700;color:var(--bg);font-size:18px;margin-top:12px}
    .spinner{width:44px;height:44px;border-radius:50%;border:4px solid rgba(10,10,10,0.08);border-top-color:var(--accent);animation:spin 1s linear infinite}
    @keyframes spin{to{transform:rotate(360deg)}}
    #loading.fade{opacity:0;pointer-events:none;transition:opacity 0.6s ease}

    /* Header */
    header{position:sticky;top:0;z-index:80;background:linear-gradient(180deg,rgba(6,10,18,0.8),rgba(6,10,18,0.6));backdrop-filter:blur(6px)}
    .nav{display:flex;align-items:center;justify-content:space-between;gap:18px;padding:14px 24px;max-width:var(--maxw);margin:0 auto}
    .brand{display:flex;align-items:center;gap:12px;color:var(--white-min);font-weight:700}
    .logo{width:44px;height:44px;border-radius:10px;background:linear-gradient(135deg,var(--accent-2),var(--accent));display:flex;align-items:center;justify-content:center;font-weight:800;color:#fff}
    nav ul{display:flex;gap:18px;align-items:center;margin:0;padding:0;list-style:none}
    nav a{color:var(--muted);font-weight:600}
    .cta{background:linear-gradient(90deg,var(--accent),var(--accent-2));color:#071022;padding:10px 14px;border-radius:10px;font-weight:700;box-shadow:0 6px 20px rgba(14,165,255,0.12);transition:transform .22s ease,box-shadow .22s ease}
    .cta:hover{transform:translateY(-4px);box-shadow:0 12px 30px rgba(14,165,255,0.18)}

    /* Hero */
    .hero{display:grid;grid-template-columns:1fr 460px;gap:36px;align-items:center;padding:72px 0}
    .hero h1{font-size:36px;line-height:1.05;margin:0;color:var(--white-min)}
    .hero p{color:var(--muted);margin-top:12px;max-width:56ch}
    .hero-ill{border-radius:12px;overflow:hidden;background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent);padding:12px}

    /* About */
    .about{display:flex;gap:22px;align-items:center;padding:28px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);border:1px solid rgba(255,255,255,0.03)}
    .about h3{margin:0;color:var(--accent)}
    .about p{margin:6px 0 0;color:var(--muted)}

    /* Sections base */
    section{padding:46px 0}
    .section-title{font-size:22px;margin-bottom:18px;color:var(--white-min)}

    /* Features & Pricing (animation applied) */
    .features-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:18px}
    .feature-card, .price-card{background:var(--card);padding:20px;border-radius:12px;border:1px solid rgba(255,255,255,0.03);box-shadow:0 8px 30px rgba(2,6,23,0.6);transform:scale(.98);opacity:0}
    .feature-card h4, .price-card h4{margin:0 0 8px;color:var(--accent)}
    .feature-card p, .price-card p{color:var(--muted);margin:0}

    /* visible class when animated */
    .is-visible{opacity:1;transform:scale(1);transition:opacity .8s ease, transform .8s cubic-bezier(.2,.9,.2,1)}

    /* Contact & forms */
    .contact-card{background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);padding:20px;border-radius:12px;border:1px solid rgba(255,255,255,0.03);}
    label{display:block;color:var(--muted);font-size:13px;margin-bottom:6px}
    input,textarea{width:100%;padding:12px;border-radius:10px;border:1px solid rgba(255,255,255,0.06);background:transparent;color:var(--white-min)}
    .btn-primary{background:linear-gradient(90deg,var(--accent),var(--accent-2));color:#071022;padding:12px 16px;border-radius:10px;border:none;font-weight:700;cursor:pointer;transition:transform .18s ease,box-shadow .18s ease}
    .btn-primary:hover{transform:translateY(-4px);box-shadow:0 10px 30px rgba(14,165,255,0.12)}

    /* Footer */
    footer{padding:28px;text-align:center;color:var(--muted);border-top:1px solid rgba(255,255,255,0.02)}

    /* Responsive: mobile layout vertical and larger buttons */
    @media(max-width:900px){
      .hero{grid-template-columns:1fr;gap:18px;text-align:left;padding:36px 12px}
      .hero h1{font-size:28px}
      .nav{padding:14px 16px}
      nav ul{display:none}
      .cta{padding:12px 16px}
      .btn-primary{width:100%;padding:14px}
    }

  </style>
</head>
<body>
  <!-- Loading screen (white minimal) -->
  <div id="loading">
    <div class="spinner" aria-hidden="true"></div>
    <div class="load-mark">Memuat <strong>LAYANAN VPN BUNNY</strong>…</div>
  </div>

  <header>
    <div class="nav container">
      <div class="brand"><div class="logo">🐰</div>LAYANAN VPN BUNNY</div>
      <nav>
        <ul>
          <li><a href="about.html">Tentang</a></li>
          <li><a href="fitur.html">Fitur</a></li>
          <li><a href="harga.html">Harga</a></li>
          <li><a href="kontak.html" class="cta">Hubungi</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main class="container">
    <!-- HERO -->
    <section class="hero">
      <div>
        <h1>Koneksi Aman untuk Perusahaan — Privasi & Kontrol</h1>
        <p>Menyediakan solusi VPN yang aman, terkelola, dan sesuai standar industri untuk mendukung operasi bisnis dan perlindungan data sensitif.</p>
        <div style="margin-top:18px;display:flex;gap:12px;flex-wrap:wrap">
          <a href="harga.html" class="cta">Mulai Sekarang</a>
          <a href="fitur.html" style="color:var(--muted);padding:10px 14px;border-radius:10px;border:1px solid rgba(255,255,255,0.03)">Pelajari Fitur</a>
        </div>
      </div>
      <div class="hero-ill">
        <img src="Kelinci.jpeg" alt="Illustration" style="width:100%;border-radius:8px;display:block">
      </div>
    </section>

      <footer>
    <div class="container">© <span id="year"></span> LAYANAN VPN BUNNY — Semua hak dilindungi.</div>
  </footer>

  <script>
    // loading
    window.addEventListener('load', ()=>{
      const ld = document.getElementById('loading');
      setTimeout(()=> ld.classList.add('fade'), 600);
      setTimeout(()=> ld.remove(), 1300);
    });

    // set year
    document.getElementById('year').textContent = new Date().getFullYear();

    // IntersectionObserver for zoom+fade (0.8s) with replay
    const animEls = document.querySelectorAll('[data-anim]');
    const obsOptions = {threshold: 0.15};
    const observer = new IntersectionObserver((entries)=>{
      entries.forEach(entry=>{
        const el = entry.target;
        if(entry.isIntersecting){
          el.classList.add('is-visible');
        } else {
          // replay when re-entering
          el.classList.remove('is-visible');
        }
      });
    }, obsOptions);
    animEls.forEach(el=>observer.observe(el));

    // Contact form simple handler
    document.getElementById('contactForm').addEventListener('submit', e=>{
      e.preventDefault();
      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();
      const msg = document.getElementById('message').value.trim();
      const out = document.getElementById('contactMsg');
      if(!name || !email){ out.textContent = 'Nama dan email wajib diisi.'; out.style.color = '#f97316'; return; }
      out.textContent = 'Terima kasih — permintaan Anda telah terkirim. Tim sales akan menghubungi.';
      out.style.color = 'var(--accent)';
      // integration: POST to backend endpoint here
      e.target.reset();
    });

  </script>
</body>
</html>
