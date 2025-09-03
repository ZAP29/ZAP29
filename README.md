<!DOCTYPE html>
<html lang="es" dir="ltr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Diego Alejandro Zapata Urrego — Portfolio</title>
  <meta name="description" content="Desarrollador backend con experiencia en Java (Spring Boot), Python, Node.js, C++ (embebidos) y desarrollo web con JavaScript y Vue.js. Décimo semestre de Ingeniería de Sistemas." />

  <!-- Open Graph / Twitter -->
  <meta property="og:title" content="Diego Alejandro Zapata Urrego — Portfolio" />
  <meta property="og:description" content="Backend • Embebidos • Arquitectura de software • Web moderna" />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://your-domain.example/" />
  <meta property="og:image" content="https://your-domain.example/og-image.png" />
  <meta name="twitter:card" content="summary_large_image" />

  <!-- Fonts (optional, safe fallbacks provided) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

  <style>
    :root {
      --bg: #0b0f14;
      --card: #0f1620;
      --muted: #9fb1c1;
      --text: #e6f1ff;
      --accent: #4cc9f0;
      --accent-2: #80ffea;
      --ring: rgba(76, 201, 240, 0.35);
      --chip: #13202e;
      --chip-border: #223445;
      --ok: #7dd3fc;
      --warn: #fcd34d;
      --good: #86efac;
      --shadow: 0 12px 30px rgba(0,0,0,.35), inset 0 1px 0 rgba(255,255,255,.02);
    }

    [data-theme="light"] {
      --bg: #f7fafc;
      --card: #ffffff;
      --muted: #4a5568;
      --text: #111827;
      --accent: #2563eb;
      --accent-2: #0891b2;
      --ring: rgba(37, 99, 235, .25);
      --chip: #f1f5f9;
      --chip-border: #e2e8f0;
      --shadow: 0 10px 24px rgba(2, 6, 23, .08), inset 0 1px 0 rgba(255,255,255,.6);
    }

    * { box-sizing: border-box; }
    html, body { height: 100%; }
    body {
      margin: 0;
      background: radial-gradient(800px 600px at 20% -10%, rgba(76,201,240,.12), transparent 60%),
                  radial-gradient(900px 700px at 120% 10%, rgba(128,255,234,.10), transparent 60%),
                  var(--bg);
      color: var(--text);
      font: 400 16px/1.6 Inter, system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, "Helvetica Neue", Arial, "Apple Color Emoji", "Segoe UI Emoji";
      letter-spacing: .2px;
    }

    .container { max-width: 1100px; margin: 0 auto; padding: 28px 18px 64px; }

    /* Header */
    header {
      display: grid; grid-template-columns: 1fr auto; gap: 16px; align-items: center; margin-bottom: 22px;
    }
    .brand { display:flex; align-items:center; gap:14px; }
    .avatar {
      width: 56px; height: 56px; border-radius: 16px; background: linear-gradient(135deg,var(--accent),var(--accent-2));
      box-shadow: var(--shadow);
    }
    h1 { font-size: clamp(22px, 1.8vw + 16px, 34px); margin: 0; letter-spacing: .2px; }
    .subtitle { margin: 2px 0 0; color: var(--muted); font-weight: 500; font-size: 14px; }

    .header-actions { display:flex; gap: 8px; align-items:center; }
    .btn {
      appearance: none; border: 1px solid transparent; background: var(--accent); color: white; font-weight: 600;
      padding: 10px 14px; border-radius: 12px; cursor: pointer; box-shadow: var(--shadow);
      transition: transform .15s ease, box-shadow .2s ease, background .2s ease;
    }
    .btn.secondary { background: transparent; color: var(--text); border-color: var(--chip-border); }
    .btn:hover { transform: translateY(-1px); }

    /* Grid */
    .grid { display:grid; grid-template-columns: 1.1fr .9fr; gap: 16px; }
    @media (max-width: 950px) { .grid { grid-template-columns: 1fr; } }

    /* Cards */
    .card {
      background: linear-gradient(180deg, rgba(255,255,255,.02), rgba(0,0,0,.02)), var(--card);
      border: 1px solid rgba(255,255,255,.06);
      border-color: var(--chip-border);
      border-radius: 18px; padding: 18px 18px; box-shadow: var(--shadow);
    }
    .card h2 { margin: 2px 2px 12px; font-size: 18px; letter-spacing:.25px; }
    .muted { color: var(--muted); }

    .chips { display:flex; flex-wrap: wrap; gap: 8px; }
    .chip {
      border: 1px solid var(--chip-border); background: var(--chip); color: var(--text);
      padding: 7px 10px; border-radius: 12px; font-size: 13px; font-weight: 600; letter-spacing:.2px;
    }

    /* Sections */
    .lead { font-size: clamp(16px, .6vw + 14px, 18px); color: var(--muted); }

    .list { display: grid; gap: 12px; }
    .item { display:grid; gap: 4px; padding: 12px; border-radius: 14px; border: 1px dashed var(--chip-border); background: rgba(255,255,255,.02); }
    .item .title { font-weight: 700; }
    .item .meta { color: var(--muted); font-size: 13px; }
    .item .desc { margin-top: 6px; }

    .tags { display:flex; flex-wrap:wrap; gap:6px; margin-top:8px; }
    .tag { font-size:12px; border:1px solid var(--chip-border); background: var(--chip); padding:4px 8px; border-radius:10px; }

    /* Timeline */
    .timeline { position: relative; padding-left: 18px; }
    .timeline::before { content: ""; position: absolute; left: 6px; top: 6px; bottom: 6px; width: 2px; background: linear-gradient(var(--accent), transparent); opacity:.6; }
    .t-item { position: relative; margin: 0 0 14px 0; }
    .t-item::before { content: ""; position:absolute; left:-14px; top:8px; width:10px; height:10px; border-radius:50%; background: var(--accent); box-shadow: 0 0 0 3px var(--ring); }

    /* Footer */
    footer { margin-top: 28px; color: var(--muted); font-size: 14px; display:flex; justify-content: space-between; align-items: center; gap:12px; flex-wrap: wrap; }
    .links { display:flex; gap: 10px; flex-wrap: wrap; }
    .link { color: var(--text); text-decoration: none; border:1px solid var(--chip-border); background: var(--chip); padding:8px 10px; border-radius: 10px; font-weight: 600; }

    /* Accessibility */
    .sr-only { position:absolute; width:1px; height:1px; padding:0; margin:-1px; overflow:hidden; clip:rect(0,0,0,0); white-space:nowrap; border:0; }
  </style>

  <!-- Schema.org Person -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "Person",
    "name": "Diego Alejandro Zapata Urrego",
    "jobTitle": "Backend Developer / Embedded Systems",
    "email": "mailto:dialzaur29@gmail.com",
    "telephone": "+57 3122239241",
    "address": {
      "@type": "PostalAddress",
      "addressLocality": "La Virginia",
      "addressRegion": "Risaralda",
      "addressCountry": "CO"
    },
    "sameAs": ["https://www.linkedin.com/in/your-custom-link"]
  }
  </script>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="avatar" aria-hidden="true"></div>
        <div>
          <h1>Diego Alejandro Zapata Urrego</h1>
          <p class="subtitle">Backend • Embedded • Software Architecture • Web</p>
        </div>
      </div>
      <div class="header-actions">
        <button class="btn" id="themeToggle" aria-label="Cambiar tema">Toggle theme</button>
        <a class="btn secondary" href="mailto:dialzaur29@gmail.com">Contactar</a>
        <a class="btn" href="#cv" id="downloadCV">Descargar CV</a>
      </div>
    </header>

    <section class="card" aria-labelledby="about-title">
      <h2 id="about-title">Resumen</h2>
      <p class="lead">
        Décimo semestre de Ingeniería de Sistemas. Experiencia en backend con <strong>Java (Spring Boot)</strong>, <strong>Python</strong> y <strong>Node.js</strong>, desarrollo de <strong>sistemas embebidos con C++</strong> e interfaces web con <strong>JavaScript, Vue.js y Tailwind CSS</strong>. Conocimientos en <strong>arquitectura de software</strong> desde el levantamiento de requisitos hasta la implementación, y en <strong>analítica y visualización de datos</strong> con Python (pandas, NumPy, Matplotlib) y R. Integración eficiente de hardware y software, enfoque en escalabilidad y calidad.
      </p>
      <div class="chips" aria-label="Contact">
        <span class="chip">📍 La Virginia, Risaralda</span>
        <a class="chip" href="mailto:dialzaur29@gmail.com">✉️ dialzaur29@gmail.com</a>
        <a class="chip" href="tel:+573122239241">📱 +57 312 223 9241</a>
        <a class="chip" href="https://www.linkedin.com/in/your-custom-link" target="_blank" rel="noreferrer noopener">🔗 LinkedIn</a>
        <a class="chip" href="https://github.com/your-github" target="_blank" rel="noreferrer noopener">🐙 GitHub</a>
      </div>
    </section>

    <div class="grid">
      <section class="card" aria-labelledby="skills-title">
        <h2 id="skills-title">Habilidades</h2>
        <div class="list">
          <div class="item">
            <div class="title">Lenguajes y Frameworks</div>
            <div class="desc chips">
              <span class="chip">Java</span>
              <span class="chip">Spring Boot</span>
              <span class="chip">Python</span>
              <span class="chip">Node.js</span>
              <span class="chip">C++ (Embebidos)</span>
              <span class="chip">JavaScript</span>
              <span class="chip">Vue.js</span>
              <span class="chip">Tailwind CSS</span>
            </div>
          </div>
          <div class="item">
            <div class="title">Datos y Bases de Datos</div>
            <div class="desc chips">
              <span class="chip">SQL</span>
              <span class="chip">MySQL</span>
              <span class="chip">SQL Server</span>
              <span class="chip">Oracle</span>
              <span class="chip">MongoDB (NoSQL)</span>
              <span class="chip">Pandas</span>
              <span class="chip">NumPy</span>
              <span class="chip">Matplotlib</span>
              <span class="chip">R</span>
            </div>
          </div>
          <div class="item">
            <div class="title">Arquitectura y Prácticas</div>
            <div class="desc chips">
              <span class="chip">Arquitectura de Software</span>
              <span class="chip">Levantamiento de requisitos</span>
              <span class="chip">Diseño modular</span>
              <span class="chip">APIs REST</span>
              <span class="chip">MVC</span>
              <span class="chip">Agile / Scrum</span>
              <span class="chip">Git</span>
              <span class="chip">Docker</span>
              <span class="chip">Postman</span>
            </div>
          </div>
          <div class="item">
            <div class="title">Idiomas</div>
            <div class="desc chips">
              <span class="chip">Español (nativo)</span>
              <span class="chip">Inglés (intermedio: lectura técnica, escritura estructurada)</span>
            </div>
          </div>
        </div>
      </section>

      <section class="card" aria-labelledby="experience-title">
        <h2 id="experience-title">Experiencia</h2>
        <div class="timeline">
          <div class="t-item">
            <div class="item">
              <div class="title">Desarrollador de Aplicaciones — Independiente</div>
              <div class="meta">Mar 2022 — Actualidad</div>
              <div class="desc">
                Desarrollo de software a medida (web y escritorio), desde el análisis y levantamiento de requisitos hasta la implementación y despliegue. Diseño de arquitecturas con Java, Python y Node.js. Integración de bases de datos (MySQL, SQL Server) y mejora del rendimiento de consultas.
                <div class="tags">
                  <span class="tag">Java</span>
                  <span class="tag">Python</span>
                  <span class="tag">Node.js</span>
                  <span class="tag">SQL</span>
                  <span class="tag">Arquitectura</span>
                </div>
              </div>
            </div>
          </div>
          <div class="t-item">
            <div class="item">
              <div class="title">Proyectos Clave</div>
              <div class="meta">Logros</div>
              <div class="desc">
                <strong>Sistema de Monitoreo de Mascotas:</strong> integración hardware/software para datos en tiempo real (ubicación y signos vitales).<br>
                <strong>Aplicación Web de Gestión Empresarial:</strong> automatización de inventario y facturación para PyMEs, mejorando eficiencia y tiempos.
                <div class="tags">
                  <span class="tag">C++</span><span class="tag">IoT</span><span class="tag">Node.js</span><span class="tag">SQL</span><span class="tag">Java</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>

    <div class="grid">
      <section class="card" aria-labelledby="projects-title">
        <h2 id="projects-title">Proyectos</h2>
        <div class="list">
          <article class="item">
            <div class="title">Pet Monitoring System (IoT)</div>
            <div class="meta">C++ • Node.js • SQL</div>
            <p class="desc">Sistema con collar inteligente que captura ubicación y signos vitales en tiempo real. Backend en Node.js y almacenamiento en base de datos relacional. Integración de hardware, protocolos de comunicación y panel web.</p>
            <div class="tags">
              <span class="tag">Embebidos</span><span class="tag">Tiempo real</span><span class="tag">API REST</span>
            </div>
          </article>
          <article class="item">
            <div class="title">Business Management Web App</div>
            <div class="meta">Java • Spring Boot • MySQL</div>
            <p class="desc">Aplicación para inventario y facturación con autenticación, roles y reportes. Diseño de arquitectura modular, endpoints REST y optimización de consultas SQL.</p>
            <div class="tags">
              <span class="tag">Spring Boot</span><span class="tag">Seguridad</span><span class="tag">SQL</span>
            </div>
          </article>
        </div>
      </section>

      <section class="card" aria-labelledby="education-title">
        <h2 id="education-title">Educación & Certificaciones</h2>
        <div class="list">
          <div class="item">
            <div class="title">Ingeniería de Sistemas — Universidad Libre (Pereira)</div>
            <div class="meta">Décimo semestre — 2021 · Actualidad</div>
          </div>
          <div class="item">
            <div class="title">Bachiller Académico — Colegio La Salle (Pereira)</div>
            <div class="meta">2014 · 2020</div>
          </div>
          <div class="item">
            <div class="title">Certificaciones</div>
            <ul class="desc" style="margin:6px 0 0 18px;">
              <li>Formación SQL con MySQL — ONE Oracle Next Education (2023)</li>
              <li>Oracle Cloud Infrastructure — ONE Oracle Next Education (2023)</li>
              <li>Integración de Aplicaciones Java con Bases de Datos — ONE (2023)</li>
              <li>Java Orientado a Objetos / Spring Boot 3 (G4) — ONE (2023)</li>
              <li>SQL (Intermedio) — HackerRank (2024)</li>
              <li>Certificación en Ciberseguridad — MinTIC TalentoTech (2025)</li>
            </ul>
          </div>
        </div>
      </section>
    </div>

    <section class="card" aria-labelledby="contact-title">
      <h2 id="contact-title">Contacto</h2>
      <p class="lead">¿Hablamos de un proyecto o práctica? Escríbeme o agenda una llamada.</p>
      <div class="chips">
        <a class="chip" href="mailto:dialzaur29@gmail.com">Enviar correo</a>
        <a class="chip" href="https://www.linkedin.com/in/your-custom-link" target="_blank" rel="noreferrer noopener">Perfil en LinkedIn</a>
        <a class="chip" href="https://github.com/your-github" target="_blank" rel="noreferrer noopener">Repositorio GitHub</a>
      </div>
    </section>

    <footer>
      <span>© <span id="year"></span> Diego Alejandro Zapata Urrego</span>
      <div class="links">
        <a class="link" href="#">Aviso de privacidad</a>
        <a class="link" href="#">Términos</a>
      </div>
    </footer>
  </div>

  <script>
    // Theme toggle with persistence
    (function() {
      const STORAGE_KEY = 'theme-preference';
      const getStored = () => localStorage.getItem(STORAGE_KEY);
      const setStored = (v) => localStorage.setItem(STORAGE_KEY, v);
      const applyTheme = (v) => document.body.setAttribute('data-theme', v);

      const prefersLight = window.matchMedia('(prefers-color-scheme: light)').matches;
      const initial = getStored() || (prefersLight ? 'light' : 'dark');
      applyTheme(initial);

      document.getElementById('themeToggle').addEventListener('click', () => {
        const next = document.body.getAttribute('data-theme') === 'dark' ? 'light' : 'dark';
        applyTheme(next); setStored(next);
      });
    })();

    // Year & dummy CV link
    document.getElementById('year').textContent = new Date().getFullYear();
    document.getElementById('downloadCV').addEventListener('click', (e) => {
      const cv = document.getElementById('cv');
      if (!cv) {
        e.preventDefault();
        alert('Sube tu CV como PDF a este repositorio y cambia el enlace del botón.');
      }
    });
  </script>
</body>
</html>
