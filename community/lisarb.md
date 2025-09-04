<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Portfólio - Antônio Lisarb</title>
  <style>
    :root {
      --primary: #2563eb;
      --secondary: #1e40af;
      --bg: #f9fafb;
      --card-bg: #ffffff;
      --text: #1f2937;
      --muted: #6b7280;
      --white: #ffffff;
    }

    [data-theme="dark"] {
      --bg: #111827;
      --card-bg: #1f2937;
      --text: #f3f4f6;
      --muted: #9ca3af;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: "Inter", "Segoe UI", sans-serif;
    }

    body {
      background: var(--bg);
      color: var(--text);
      line-height: 1.6;
      transition: background 0.3s, color 0.3s;
    }

    /* TOGGLE THEME */
    .theme-toggle {
      position: fixed;
      top: 1rem;
      right: 1rem;
      background: var(--primary);
      color: #fff;
      border: none;
      padding: 0.5rem 1rem;
      border-radius: 6px;
      cursor: pointer;
      font-size: 0.9rem;
      transition: background 0.3s;
      z-index: 1000;
    }

    .theme-toggle:hover {
      background: var(--secondary);
    }

    /* HERO */
    .hero {
      text-align: center;
      padding: 5rem 1.5rem 3rem;
    }

    .hero h1 {
      font-size: 2.8rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
    }

    .hero p {
      font-size: 1.2rem;
      margin-bottom: 1.5rem;
      color: var(--muted);
    }

    .actions {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      justify-content: center;
    }

    .btn {
      padding: 0.7rem 1.4rem;
      border-radius: 6px;
      background: var(--primary);
      color: #fff;
      text-decoration: none;
      font-weight: 600;
      transition: all 0.3s ease;
    }

    .btn:hover {
      background: var(--secondary);
    }

    /* SECTIONS */
    section {
      max-width: 1200px;
      margin: 3rem auto;
      padding: 0 1.5rem;
    }

    h2 {
      font-size: 2rem;
      text-align: center;
      margin-bottom: 2rem;
      font-weight: 700;
      color: var(--primary);
    }

    /* SOBRE */
    .sobre {
      background: var(--card-bg);
      padding: 2rem;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.08);
      text-align: center;
      transition: background 0.3s, color 0.3s;
    }

    .sobre p {
      font-size: 1.05rem;
      color: var(--muted);
    }

    /* GRID */
    .grid {
      display: grid;
      gap: 2rem;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    }

    /* CARD PROJETOS */
    .card {
      background: var(--card-bg);
      border-radius: 12px;
      box-shadow: 0 6px 16px rgba(0,0,0,0.08);
      overflow: hidden;
      display: flex;
      flex-direction: column;
      transition: transform 0.3s ease, box-shadow 0.3s ease, background 0.3s;
      opacity: 0;
      transform: translateY(40px);
      animation: fadeUp 0.8s forwards;
    }

    .card:hover {
      transform: translateY(-6px);
      box-shadow: 0 10px 22px rgba(0,0,0,0.12);
    }

    .card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
    }

    .card-body {
      padding: 1.5rem;
      flex: 1;
    }

    .card-body h3 {
      margin-bottom: 0.5rem;
      font-size: 1.3rem;
      color: var(--primary);
    }

    .card-body p {
      font-size: 1rem;
      color: var(--muted);
      margin-bottom: 1rem;
    }

    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
    }

    .tag {
      background: var(--primary);
      color: #fff;
      padding: 0.3rem 0.6rem;
      border-radius: 4px;
      font-size: 0.8rem;
    }

    .card-footer {
      padding: 1rem 1.5rem;
      background: #f3f4f6;
      text-align: right;
    }

    [data-theme="dark"] .card-footer {
      background: #374151;
    }

    .btn-small {
      padding: 0.5rem 1rem;
      font-size: 0.9rem;
    }

    /* TIMELINE */
    .timeline {
      position: relative;
      margin: 2rem 0;
      padding-left: 2rem;
    }

    .timeline::before {
      content: '';
      position: absolute;
      left: 10px;
      top: 0;
      bottom: 0;
      width: 3px;
      background: var(--primary);
    }

    .timeline-item {
      margin-bottom: 2rem;
      position: relative;
    }

    .timeline-item::before {
      content: '';
      position: absolute;
      left: -4px;
      top: 0.3rem;
      width: 14px;
      height: 14px;
      border-radius: 50%;
      background: var(--primary);
    }

    .timeline-item h4 {
      font-size: 1.2rem;
      color: var(--primary);
      margin-bottom: 0.3rem;
    }

    .timeline-item p {
      color: var(--muted);
      font-size: 0.95rem;
    }

    /* CONTATO */
    .contato form {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      max-width: 600px;
      margin: 0 auto;
    }

    .contato input, .contato textarea {
      padding: 0.8rem;
      border-radius: 6px;
      border: 1px solid #d1d5db;
      font-size: 1rem;
      background: var(--card-bg);
      color: var(--text);
      transition: background 0.3s, color 0.3s;
    }

    .contato button {
      padding: 0.8rem;
      background: var(--primary);
      color: var(--white);
      border: none;
      border-radius: 6px;
      font-size: 1rem;
      cursor: pointer;
      transition: background 0.3s;
    }

    .contato button:hover {
      background: var(--secondary);
    }

    /* ANIMAÇÕES */
    .card:nth-child(1) { animation-delay: 0.2s; }
    .card:nth-child(2) { animation-delay: 0.4s; }
    .card:nth-child(3) { animation-delay: 0.6s; }
    .card:nth-child(4) { animation-delay: 0.8s; }

    @keyframes fadeUp {
      from {
        opacity: 0;
        transform: translateY(40px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* FOOTER */
    footer {
      text-align: center;
      padding: 2rem 1rem;
      background: #111827;
      color: #9ca3af;
      font-size: 0.9rem;
      margin-top: 3rem;
    }

    footer a {
      color: var(--primary);
      text-decoration: none;
      margin: 0 0.5rem;
      font-weight: 500;
    }

    footer a:hover {
      color: var(--secondary);
    }
  </style>
</head>
<body>
  <button class="theme-toggle" onclick="toggleTheme()">🌙 Tema</button>

  <!-- HERO -->
  <div class="hero">
    <h1>Antônio Lisarb</h1>
    <p>Desenvolvedor Web • UX Designer • Criador de Experiências Digitais</p>
    <div class="actions">
      <a href="#" class="btn">📄 Baixar Currículo</a>
      <a href="#contato" class="btn">✉️ Contato</a>
    </div>
  </div>

  <!-- SOBRE -->
  <section>
    <h2>Sobre mim</h2>
    <div class="sobre">
      <p>Tenho 23 anos e sou estudante de Sistemas de Informação pela Uninassau. 
      Minha paixão por tecnologia e design me levou a atuar em áreas como <strong>programação web</strong>, 
      <strong>UX design</strong>, <strong>edição de vídeos</strong> e <strong>criação de artes gráficas</strong>.  
      Busco constantemente unir estética, usabilidade e tecnologia para entregar soluções de impacto.</p>
    </div>
  </section>

  <!-- EXPERIÊNCIAS -->
  <section>
    <h2>Experiência & Projetos</h2>
    <div class="grid">
      <div class="card">
        <img src="https://via.placeholder.com/600x300?text=Web+Project" alt="Projeto Web">
        <div class="card-body">
          <h3>💻 Programação Web</h3>
          <p>Desenvolvimento de interfaces modernas, responsivas e otimizadas.</p>
          <div class="tags">
            <span class="tag">HTML</span>
            <span class="tag">CSS</span>
            <span class="tag">JavaScript</span>
          </div>
        </div>
        <div class="card-footer">
          <a href="#" class="btn btn-small">Ver Projeto</a>
        </div>
      </div>

      <div class="card">
        <img src="https://via.placeholder.com/600x300?text=UX+Design" alt="Protótipo UX">
        <div class="card-body">
          <h3>🎨 UX Design</h3>
          <p>Design centrado no usuário, aplicando usabilidade e acessibilidade.</p>
          <div class="tags">
            <span class="tag">Figma</span>
            <span class="tag">Adobe XD</span>
          </div>
        </div>
        <div class="card-footer">
          <a href="#" class="btn btn-small">Ver Protótipo</a>
        </div>
      </div>

      <div class="card">
        <img src="https://via.placeholder.com/600x300?text=Video+Editing" alt="Vídeo editado">
        <div class="card-body">
          <h3>✂️ Edição de Vídeos</h3>
          <p>Produção criativa de vídeos para mídias sociais e apresentações.</p>
          <div class="tags">
            <span class="tag">Premiere</span>
            <span class="tag">After Effects</span>
          </div>
        </div>
        <div class="card-footer">
          <a href="#" class="btn btn-small">Assistir Vídeo</a>
        </div>
      </div>

      <div class="card">
        <img src="https://via.placeholder.com/600x300?text=Graphic+Design" alt="Artes Gráficas">
        <div class="card-body">
          <h3>🖌️ Artes Gráficas</h3>
          <p>Criação de materiais visuais impactantes para redes sociais.</p>
          <div class="tags">
            <span class="tag">Canva</span>
            <span class="tag">CorelDRAW</span>
          </div>
        </div>
        <div class="card-footer">
          <a href="#" class="btn btn-small">Ver Artes</a>
        </div>
      </div>
    </div>
  </section>

  <!-- TIMELINE -->
  <section>
    <h2>Minha Trajetória</h2>
    <div class="timeline">
      <div class="timeline-item">
        <h4>2022 - Presente</h4>
        <p>Cursando Sistemas de Informação na Uninassau.</p>
      </div>
      <div class="timeline-item">
        <h4>2021</h4>
        <p>Início de projetos em UX Design e criação de artes gráficas.</p>
      </div>
      <div class="timeline-item">
        <h4>2020</h4>
        <p>Experiência inicial com programação web e edição de vídeos.</p>
      </div>
    </div>
  </section>

  <!-- CONTATO -->
  <section id="contato" class="contato">
    <h2>Entre em Contato</h2>
    <form action="#" method="POST">
      <input type="text" name="nome" placeholder="Seu nome" required>
      <input type="email" name="email" placeholder="Seu e-mail" required>
      <textarea name="mensagem" rows="5" placeholder="Sua mensagem" required></textarea>
      <button type="submit">Enviar</button>
    </form>
  </section>

  <!-- FOOTER -->
  <footer>
    © 2025 - Desenvolvido por Antônio Lisarb  
    <br>
    <a href="https://www.linkedin.com/in/antonio-lisarb-cordeiro-saraiva-a95818238/">LinkedIn</a> | <a href="https://github.com/lisarb-saraiva">GitHub</a> | <a href="https://www.behance.net/antniosaraiva2">Behance</a>
  </footer>

  <script>
    function toggleTheme() {
      const body = document.body;
      const currentTheme = body.getAttribute("data-theme");
      if (currentTheme === "dark") {
        body.removeAttribute("data-theme");
      } else {
        body.setAttribute("data-theme", "dark");
      }
    }
  </script>
</body>
</html>
