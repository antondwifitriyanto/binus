<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Open Sharing Knowledge</title>
  <meta name="description" content="Portal berbagi pengetahuan terbuka untuk ekonomi, AI, dan keberlanjutan. Pelajari, pakai, dan kontribusikan." />
  <meta property="og:title" content="Open Sharing Knowledge" />
  <meta property="og:description" content="Portal berbagi pengetahuan terbuka: belajar, gunakan, dan berkontribusi." />
  <meta property="og:type" content="website" />
  <meta property="og:image" content="./og-image.png" />
  <meta name="color-scheme" content="light dark" />
  <link rel="icon" href="./favicon.png" />
  <style>
    :root{
      --bg: #0b1220;      /* dasar gelap elegan */
      --card:#0f172a;     /* slate-900 */
      --muted:#94a3b8;    /* slate-400 */
      --text:#e2e8f0;     /* slate-200 */
      --brand:#22d3ee;    /* cyan-400 */
      --brand-2:#34d399;  /* emerald-400 */
      --accent: #f59e0b;  /* amber-500 */
      --ring: rgba(34,211,238,.35);
      --shadow: 0 10px 30px rgba(0,0,0,.35);
    }
    @media (prefers-color-scheme: light){
      :root{ --bg:#f8fafc; --card:#ffffff; --text:#0f172a; --muted:#475569; --shadow:0 10px 25px rgba(2,6,23,.08);}    }
    *{box-sizing:border-box}
    html,body{margin:0;padding:0;font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, Helvetica Neue, Arial, "Apple Color Emoji", "Segoe UI Emoji"; background:var(--bg); color:var(--text);}
    a{color:var(--brand); text-decoration:none}
    a:hover{text-decoration:underline}
    .container{width:min(1100px, 92vw); margin:auto}
    header{position:sticky; top:0; backdrop-filter:saturate(150%) blur(8px); background:color-mix(in srgb, var(--bg) 85%, transparent); border-bottom:1px solid rgba(148,163,184,.15); z-index:50}
    .nav{display:flex; align-items:center; justify-content:space-between; padding:14px 0}
    .nav a.logo{font-weight:800; letter-spacing:.2px; color:var(--text);}
    .nav .links a{margin-left:18px; color:var(--muted)}
    .btn{display:inline-block; padding:12px 16px; border-radius:14px; border:1px solid rgba(148,163,184,.25); background:linear-gradient(180deg, color-mix(in srgb, var(--card) 88%, black), var(--card)); color:var(--text); box-shadow: var(--shadow); transition: transform .15s ease, box-shadow .2s ease; }
    .btn:hover{ transform: translateY(-1px); box-shadow: 0 14px 36px rgba(0,0,0,.35)}
    .btn.brand{ border-color: color-mix(in srgb, var(--brand) 60%, transparent); background:linear-gradient(180deg, color-mix(in srgb, var(--brand) 18%, var(--card)), var(--card)); }

    .hero{ padding:90px 0 60px; position:relative; overflow:hidden}
    .hero .glow{ position:absolute; inset:auto -20% -30% -20%; height:60vh; background:radial-gradient(60% 60% at 50% 0%, color-mix(in srgb, var(--brand) 25%, transparent), transparent 60%), radial-gradient(40% 40% at 60% 30%, color-mix(in srgb, var(--brand-2) 20%, transparent), transparent 70%);}    
    .hero h1{ font-size: clamp(2rem, 1.4rem + 2.6vw, 3.4rem); line-height:1.05; margin:0 0 16px; letter-spacing:.2px}
    .hero p{ margin:0 0 28px; color:var(--muted); max-width:800px}
    .tag{display:inline-flex; align-items:center; gap:8px; padding:6px 10px; border-radius:999px; border:1px solid rgba(148,163,184,.25); color:var(--muted); margin-bottom:16px}
    .tag b{color:var(--brand)}

    .grid{ display:grid; grid-template-columns: repeat(12, 1fr); gap:22px}
    .card{ grid-column: span 4; background:var(--card); border:1px solid rgba(148,163,184,.15); border-radius:18px; padding:18px; box-shadow: var(--shadow)}
    .card h3{ margin:8px 0 10px; font-size:1.1rem}
    .card p{ color:var(--muted); margin:0}

    @media (max-width: 950px){ .card{ grid-column: span 6 } }
    @media (max-width: 640px){ .card{ grid-column: span 12 } }

    section{ padding:48px 0 }
    section h2{ font-size: clamp(1.25rem, 1.1rem + 1.2vw, 2rem); margin:0 0 14px}
    .muted{ color:var(--muted) }

    .list{ display:grid; grid-template-columns: repeat(12, 1fr); gap:18px }
    .item{ grid-column: span 6; background:var(--card); border:1px solid rgba(148,163,184,.15); border-radius:16px; padding:16px }
    .item small{ color:var(--muted) }
    .item h4{ margin:6px 0 8px; font-size:1rem }

    .callout{ display:grid; grid-template-columns: 1fr; gap:14px; background:linear-gradient(180deg, color-mix(in srgb, var(--brand) 10%, var(--card)), var(--card)); border:1px solid color-mix(in srgb, var(--brand) 30%, transparent); border-radius:18px; padding:22px}

    .kbd{ font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace; padding:2px 6px; border-radius:8px; border:1px solid rgba(148,163,184,.35); color:var(--text); background:color-mix(in srgb, var(--card) 85%, #0002) }
    footer{ border-top:1px solid rgba(148,163,184,.15); padding:22px 0 60px; color:var(--muted) }

    .pill{display:inline-flex; align-items:center; gap:8px; padding:8px 12px; border-radius:999px; border:1px solid rgba(148,163,184,.2);}
    .pill .dot{width:8px; height:8px; border-radius:999px; background:var(--brand-2)}

    .backtotop{ position:fixed; right:18px; bottom:18px; border-radius:999px; width:46px; height:46px; display:grid; place-items:center; box-shadow:var(--shadow); background:var(--card); border:1px solid rgba(148,163,184,.2); opacity:0; transform:translateY(8px); transition: all .2s ease }
    .backtotop.show{ opacity:1; transform:none }
  </style>
  <script type="application/ld+json">
  {
    "@context":"https://schema.org",
    "@type":"WebSite",
    "name":"Open Sharing Knowledge",
    "url":"https://<username>.github.io/",
    "description":"Portal berbagi pengetahuan terbuka untuk ekonomi, AI, dan keberlanjutan.",
    "potentialAction":{"@type":"SearchAction","target":"https://<username>.github.io/?q={search_term_string}","query-input":"required name=search_term_string"}
  }
  </script>
</head>
<body>
  <header>
    <div class="container nav">
      <a class="logo" href="#">Open Sharing Knowledge</a>
      <nav class="links">
        <a href="#principles">Prinsip</a>
        <a href="#knowledge">Knowledge</a>
        <a href="#projects">Proyek</a>
        <a href="#license">Lisensi</a>
        <a class="btn" href="#contribute">Kontribusi</a>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero">
      <div class="glow" aria-hidden="true"></div>
      <div class="container">
        <span class="tag"><span class="dot" style="background:var(--brand)"></span> Inisiatif Terbuka · <b>Learn · Use · Contribute</b></span>
        <h1>Berbagi Pengetahuan Secara Terbuka<br/>untuk <span style="color:var(--brand)">Ekonomi</span>, <span style="color:var(--brand-2)">AI</span>, dan <span style="color:var(--accent)">Keberlanjutan</span>.</h1>
        <p>Semua materi, template, dan simulasi tersedia gratis. Gunakan untuk belajar, dipakai dalam proyek, atau dikembangkan kembali. Mari membangun ekosistem ilmu yang <em>reproducible</em>, terbuka, dan inklusif.</p>
        <div style="display:flex; gap:12px; flex-wrap:wrap">
          <a class="btn brand" href="#knowledge">Jelajahi Knowledge</a>
          <a class="btn" href="https://github.com/<username>/<repo>" target="_blank" rel="noopener">GitHub Repo</a>
        </div>
      </div>
    </section>

    <section id="principles">
      <div class="container">
        <h2>Prinsip Dasar</h2>
        <p class="muted">Kami menerapkan empat pilar dalam setiap rilis konten dan kode.</p>
        <div class="grid" style="margin-top:10px">
          <article class="card">
            <div class="pill"><span class="dot"></span><strong>Open Access</strong></div>
            <h3>Akses untuk Semua</h3>
            <p>Kode dan materi dapat diakses gratis, tanpa paywall. Gunakan untuk belajar, riset, dan implementasi bisnis.</p>
          </article>
          <article class="card">
            <div class="pill"><span class="dot"></span><strong>Reproducible</strong></div>
            <h3>Dapat Direplikasi</h3>
            <p>File, <span class="kbd">README</span>, dan <span class="kbd">requirements</span> disediakan agar hasil bisa diulang dan diverifikasi.</p>
          </article>
          <article class="card">
            <div class="pill"><span class="dot"></span><strong>Interoperable</strong></div>
            <h3>Mudah Diintegrasikan</h3>
            <p>Struktur folder dan lisensi jelas; memudahkan integrasi ke pipeline data, web, atau pembelajaran.</p>
          </article>
          <article class="card">
            <div class="pill"><span class="dot"></span><strong>Inclusive</strong></div>
            <h3>Terbuka & Inklusif</h3>
            <p>Pedoman kontribusi mendorong partisipasi lintas latar belakang—mahasiswa, peneliti, dan praktisi.</p>
          </article>
          <article class="card">
            <div class="pill"><span class="dot"></span><strong>Attribution</strong></div>
            <h3>Pengakuan Karya</h3>
            <p>Konten mengikuti CC BY 4.0, kode MIT. Mohon atribusi saat dipakai ulang.</p>
          </article>
          <article class="card">
            <div class="pill"><span class="dot"></span><strong>Quality</strong></div>
            <h3>Kurasi & QA</h3>
            <p>Template kurasi memastikan konsistensi mutu, sitasi, dan dokumentasi.</p>
          </article>
        </div>
      </div>
    </section>

    <section id="knowledge">
      <div class="container">
        <h2>Knowledge Library</h2>
        <p class="muted">Kumpulan catatan, template, dan simulasi. Ganti tautan di bawah dengan file Anda di repo GitHub.</p>
        <div class="list" style="margin-top:8px">
          <a class="item" href="./notes/economics-for-business.html">
            <small>Catatan</small>
            <h4>Economics for Business — Ringkasan & Studi Kasus</h4>
            <p class="muted">Konsep inti: permintaan, penawaran, elastisitas, kebijakan, pasar global.</p>
          </a>
          <a class="item" href="./simulations/coffee-shop/index.html">
            <small>Simulasi</small>
            <h4>Coffee Shop Inc — Simulasi Keputusan Bulanan</h4>
            <p class="muted">Latih strategi harga, promosi, COGS, dan SDM untuk profitabilitas.</p>
          </a>
          <a class="item" href="./templates/policy-brief.pdf">
            <small>Template</small>
            <h4>Policy Brief — Green Economy & Carbon</h4>
            <p class="muted">Struktur siap pakai untuk kebijakan publik dan advokasi daerah.</p>
          </a>
          <a class="item" href="./tutorials/ai-notebook.ipynb">
            <small>Tutorial</small>
            <h4>Notebook: AI untuk Ekonomi Digital</h4>
            <p class="muted">Contoh analitik pemasaran & prediksi permintaan dengan ML.</p>
          </a>
        </div>
      </div>
    </section>

    <section id="projects">
      <div class="container">
        <h2>Proyek & Roadmap</h2>
        <div class="grid">
          <article class="card" style="grid-column: span 8">
            <h3>Roadmap 2025</h3>
            <ul class="muted">
              <li>Q1: Rilis simulasi dasar (pricing, COGS, break-even).</li>
              <li>Q2: Tambah modul kebijakan publik & ekonomi karbon.</li>
              <li>Q3: Integrasi pembelajaran AI (forecast & rekomendasi).</li>
              <li>Q4: Kolaborasi kurikulum terbuka & micro-credential.</li>
            </ul>
          </article>
          <article class="card" style="grid-column: span 4">
            <h3>Status</h3>
            <p class="muted">Isu aktif, milestone, dan <em>good first issues</em> tersedia di GitHub.</p>
            <p><a class="btn" href="https://github.com/<username>/<repo>/issues" target="_blank" rel="noopener">Lihat Issues</a></p>
          </article>
        </div>
      </div>
    </section>

    <section id="license">
      <div class="container">
        <h2>Lisensi</h2>
        <div class="callout">
          <p><strong>Konten (teks, gambar, materi ajar):</strong> <a href="https://creativecommons.org/licenses/by/4.0/" target="_blank" rel="noopener">Creative Commons Attribution 4.0 (CC BY 4.0)</a> — Anda bebas berbagi dan adaptasi selama menyertakan atribusi.</p>
          <p><strong>Kode (script, template web):</strong> <a href="https://opensource.org/license/mit" target="_blank" rel="noopener">MIT License</a> — Gunakan secara komersial atau non-komersial dengan menyertakan pemberitahuan lisensi.</p>
        </div>
      </div>
    </section>

    <section id="contribute">
      <div class="container">
        <h2>Bagaimana Cara Berkontribusi?</h2>
        <ol class="muted">
          <li><strong>Fork</strong> repo GitHub ini.</li>
          <li><strong>Buat branch</strong> fitur: <span class="kbd">git checkout -b feat/nama-fitur</span></li>
          <li><strong>Commit</strong> perubahan: <span class="kbd">git commit -m "feat: tambah materi X"</span></li>
          <li><strong>Push</strong> ke origin dan <strong>buka Pull Request</strong>.</li>
        </ol>
        <p>Ikuti pedoman di <a href="./CONTRIBUTING.md">CONTRIBUTING.md</a> dan <a href="./CODE_OF_CONDUCT.md">Code of Conduct</a>.</p>
      </div>
    </section>
  </main>

  <footer>
    <div class="container" style="display:flex; align-items:center; justify-content:space-between; gap:12px; flex-wrap:wrap">
      <div>
        <strong>Open Sharing Knowledge</strong> · <span id="year"></span>
        <div class="muted">Dibangun dengan HTML+CSS murni. Tidak perlu build tools.</div>
      </div>
      <div style="display:flex; gap:12px; align-items:center">
        <a class="pill" href="https://github.com/<username>" target="_blank" rel="noopener"><span class="dot" style="background:#fff"></span> GitHub</a>
        <a class="pill" href="mailto:you@example.com"><span class="dot" style="background:#e11d48"></span> Email</a>
        <a class="pill" href="#"><span class="dot" style="background:#0ea5e9"></span> X/Twitter</a>
        <a class="pill" href="#"><span class="dot" style="background:#2563eb"></span> LinkedIn</a>
      </div>
    </div>
  </footer>

  <a href="#" class="backtotop" id="backtotop" aria-label="Kembali ke atas">↑</a>

  <script>
    // Tahun footer
    document.getElementById('year').textContent = new Date().getFullYear();

    // Tombol back-to-top
    const btt = document.getElementById('backtotop');
    document.addEventListener('scroll', () => {
      if (window.scrollY > 400) { btt.classList.add('show'); } else { btt.classList.remove('show'); }
    });

    // Konfigurasi sederhana yang mudah diedit
    const CONFIG = {
      siteTitle: 'Open Sharing Knowledge',
      repoUrl: 'https://github.com/<username>/<repo>',
      primaryEmail: 'you@example.com'
    };
    document.title = CONFIG.siteTitle;
    document.querySelector('a.logo').textContent = CONFIG.siteTitle;
    document.querySelectorAll('a[href^="https://github.com/<username>/<repo>"]').forEach(a=>a.href = CONFIG.repoUrl);
    document.querySelector('a[href^="mailto:"]').href = 'mailto:' + CONFIG.primaryEmail;
  </script>
</body>
</html>
