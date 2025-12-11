<!doctype html>
<html lang="fr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Samuel — Portfolio</title>
  <meta name="description" content="Portfolio de Samuel — UI/UX & Graphisme mobile" />
  <style>
    /* Reset simple */
    *{box-sizing:border-box;margin:0;padding:0}
    html,body{height:100%;font-family:Inter,ui-sans-serif,system-ui,-apple-system,"Helvetica Neue",Arial;line-height:1.4;color:#111}
    a{color:inherit;text-decoration:none}
    img{max-width:100%;display:block}
    /* Layout */
    :root{
      --bg:#0f1724;
      --card:#0b1220;
      --accent1:#7c3aed;
      --accent2:#06b6d4;
      --muted:#94a3b8;
    }
    body{
      background:linear-gradient(180deg,#071022 0%, #0b1220 45%, #071022 100%);
      padding:24px;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }
    .container{max-width:1100px;margin:0 auto}
    /* Nav */
    header{position:sticky;top:12px;z-index:40}
    nav{display:flex;justify-content:space-between;align-items:center;padding:10px 14px;background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);border-radius:12px;backdrop-filter: blur(6px);box-shadow: 0 6px 18px rgba(2,6,23,0.6)}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{
      width:46px;height:46px;border-radius:8px;background:linear-gradient(135deg,var(--accent1),var(--accent2));display:flex;align-items:center;justify-content:center;color:#fff;font-weight:700;font-size:18px;box-shadow:0 6px 18px rgba(124,58,237,0.18)
    }
    .nav-links{display:flex;gap:14px;align-items:center}
    .nav-links a{padding:8px 12px;border-radius:8px;color:var(--muted);font-size:14px}
    .nav-links a:hover{background:rgba(255,255,255,0.03);color:#fff}
    .btn-primary{background:linear-gradient(90deg,var(--accent1),var(--accent2));padding:8px 14px;border-radius:10px;color:white;font-weight:600}
    /* Hero */
    .hero{display:flex;gap:28px;align-items:center;margin:28px 0;padding:24px;border-radius:14px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));box-shadow:0 10px 30px rgba(2,6,23,0.6)}
    .hero-left{flex:1}
    .hero-right{width:260px}
    .avatar{width:260px;height:260px;border-radius:18px;overflow:hidden;border:4px solid rgba(255,255,255,0.03);display:flex;align-items:center;justify-content:center;background:linear-gradient(180deg,#0b1220,#081022)}
    .avatar img{width:100%;height:100%;object-fit:cover}
    h1{font-size:28px;color:#fff;margin-bottom:6px}
    p.lead{color:var(--muted);margin-bottom:14px}
    .badges{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:14px}
    .badge{background:rgba(255,255,255,0.03);padding:6px 10px;border-radius:999px;color:var(--muted);font-size:13px}
    /* Sections */
    section{margin:30px 0}
    .section-title{display:flex;justify-content:space-between;align-items:end;margin-bottom:14px}
    .section-title h2{color:#fff;font-size:20px}
    .section-title p{color:var(--muted);font-size:13px}
    /* Projects grid */
    .projects-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
    .card{background:linear-gradient(180deg, rgba(255,255,255,0.015), rgba(255,255,255,0.01));padding:14px;border-radius:12px;border:1px solid rgba(255,255,255,0.02);box-shadow:0 8px 20px rgba(2,6,23,0.6);transition:transform .22s,box-shadow .22s}
    .card:hover{transform:translateY(-6px);box-shadow:0 18px 40px rgba(2,6,23,0.7)}
    .card-img{height:160px;border-radius:10px;overflow:hidden;margin-bottom:10px;background:linear-gradient(180deg,#05060a,#0b1220);display:flex;align-items:center;justify-content:center;color:var(--muted)}
    .card h3{color:#fff;margin-bottom:8px;font-size:16px}
    .card p{color:var(--muted);font-size:14px;margin-bottom:10px}
    .card .meta{display:flex;justify-content:space-between;align-items:center;font-size:13px;color:var(--muted)}
    /* Modal */
    .modal{
      position:fixed;inset:0;display:none;align-items:center;justify-content:center;background:rgba(3,6,12,0.6);z-index:60;padding:20px;
    }
    .modal.open{display:flex}
    .modal-card{max-width:900px;width:100%;background:var(--card);padding:18px;border-radius:12px;box-shadow:0 20px 60px rgba(2,6,23,0.8);color:#fff}
    .modal-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px}
    .close-btn{background:transparent;border:0;color:var(--muted);font-size:18px;cursor:pointer}
    /* Contact */
    .contact-grid{display:grid;grid-template-columns:1fr 360px;gap:18px}
    .field{display:flex;flex-direction:column;gap:8px;margin-bottom:10px}
    input,textarea,select{padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.03);background:transparent;color:#fff;resize:vertical}
    textarea{min-height:120px}
    .socials{display:flex;gap:10px;flex-wrap:wrap}
    .chip{padding:8px 10px;border-radius:10px;background:rgba(255,255,255,0.02);color:var(--muted);font-size:13px}
    /* Footer */
    footer{margin-top:30px;padding:18px;text-align:center;color:var(--muted);font-size:13px}
    /* Responsive */
    @media (max-width:980px){
      .projects-grid{grid-template-columns:repeat(2,1fr)}
      .contact-grid{grid-template-columns:1fr}
      .hero{flex-direction:column;align-items:flex-start}
      .hero-right{width:100%}
      .avatar{width:100%;height:240px}
    }
    @media (max-width:600px){
      .projects-grid{grid-template-columns:1fr}
      nav{flex-direction:column;gap:8px}
    }

  </style>
</head>
<body>
  <div class="container">
    <header>
      <nav>
        <div class="brand">
          <div class="logo">SD</div>
          <div>
            <div style="font-weight:700;color:#fff">Samuel Design</div>
            <div style="font-size:12px;color:var(--muted)">UI/UX — Graphisme mobile</div>
          </div>
        </div>
        <div class="nav-links">
          <a href="#about">À propos</a>
          <a href="#projects">Projets</a>
          <a href="#contact">Contact</a>
          <a class="btn-primary" href="#contact">Commander</a>
        </div>
      </nav>
    </header>

    <main>
      <!-- HERO -->
      <section class="hero" id="home" aria-label="Présentation">
        <div class="hero-left">
          <h1>Samuel — Designer mobile & UI/UX</h1>
          <p class="lead">Je crée des interfaces mobiles claires, modernes et optimisées pour la conversion. Spécialiste PixelLab & outils IA pour les images.</p>

          <div class="badges" aria-hidden="true">
            <div class="badge">UI / UX</div>
            <div class="badge">Design mobile</div>
            <div class="badge">PixelLab</div>
            <div class="badge">IA — Génération d'images</div>
          </div>

          <div style="display:flex;gap:12px">
            <a class="btn-primary" href="#projects">Voir mes projets</a>
            <a style="padding:8px 12px;border-radius:10px;background:transparent;border:1px solid rgba(255,255,255,0.04);color:var(--muted)" href="Samuel_CV.pdf" download> Télécharger CV</a>
          </div>
        </div>

        <div class="hero-right">
          <div class="avatar" title="Photo de profil">
            <!-- Remplace la source par ta propre image -->
            <img src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?q=80&w=1800&auto=format&fit=crop&ixlib=rb-4.0.3&s=1a1f0e9cc8e3e9b4c3c6b100f3f3b8c7" alt="Samuel — Designer">
          </div>
        </div>
      </section>

      <!-- ABOUT -->
      <section id="about" aria-label="A propos">
        <div class="section-title">
          <h2>À propos</h2>
          <p>Expérience, méthodologie et compétences</p>
        </div>

        <div style="display:flex;gap:18px;align-items:flex-start;flex-wrap:wrap">
          <div style="flex:1;min-width:260px" class="card">
            <h3>Résumé</h3>
            <p>Designer mobile avec 4+ ans d'expérience sur projets réels : applications, identités visuelles et publicité digitale. J'accompagne les entrepreneurs du concept à la mise en ligne.</p>
            <div style="margin-top:10px" class="meta">
              <span>Localisation: Benin</span>
              <span>Freelance</span>
            </div>
          </div>

          <div style="width:300px" class="card">
            <h3>Compétences clés</h3>
            <div style="margin-top:10px;display:flex;flex-direction:column;gap:8px">
              <div class="chip">Conception d'interface</div>
              <div class="chip">Prototype & user flows</div>
              <div class="chip">PixelLab & outils mobiles</div>
              <div class="chip">Génération d'images IA</div>
            </div>
          </div>
        </div>
      </section>

      <!-- PROJECTS -->
      <section id="projects" aria-label="Projets">
        <div class="section-title">
          <h2>Projets récents</h2>
          <p>Quelques réalisations sélectionnées</p>
        </div>

        <div class="projects-grid" id="projectsGrid">
          <!-- Example project cards - remplace images/texte par ton contenu -->
          <article class="card" data-title="App Finance — Dashboard" data-img="https://images.unsplash.com/photo-1542744173-8e7e53415bb0?q=80&w=1600&auto=format&fit=crop" data-desc="Design d'un dashboard mobile pour une application finance, avec focus sur lisibilité et micro-interactions." data-tags="UI, Tableau de bord">
            <div class="card-img">Preview projet 1</div>
            <h3>App Finance — Dashboard</h3>
            <p>Interface dashboard pour suivre les dépenses et objectifs.</p>
            <div class="meta">
              <span>Mobile App</span>
              <button onclick="openProjectCard(this)" style="background:transparent;border:0;color:var(--accent2);cursor:pointer;font-weight:600">Voir</button>
            </div>
          </article>

          <article class="card" data-title="E-commerce — Basket" data-img="https://images.unsplash.com/photo-1517245386807-bb43f82c33c4?q=80&w=1600&auto=format&fit=crop" data-desc="Refonte de l'expérience panier pour augmenter la conversion sur mobile." data-tags="E-commerce, Conversion">
            <div class="card-img">Preview projet 2</div>
            <h3>E-commerce — Basket</h3>
            <p>Optimisation du parcours d'achat mobile.</p>
            <div class="meta">
              <span>Web mobile</span>
              <button onclick="openProjectCard(this)" style="background:transparent;border:0;color:var(--accent2);cursor:pointer;font-weight:600">Voir</button>
            </div>
          </article>

          <article class="card" data-title="Branding — Dori Design" data-img="https://images.unsplash.com/photo-1532619675605-2a6fa3d13f10?q=80&w=1600&auto=format&fit=crop" data-desc="Logo & guidlines pour marque de stylisme et accessoires féminins." data-tags="Logo, Branding">
            <div class="card-img">Preview projet 3</div>
            <h3>Branding — Dori Design</h3>
            <p>Identité visuelle : logo pictogramme + lettrage.</p>
            <div class="meta">
              <span>Branding</span>
              <button onclick="openProjectCard(this)" style="background:transparent;border:0;color:var(--accent2);cursor:pointer;font-weight:600">Voir</button>
            </div>
          </article>

          <!-- Tu peux dupliquer ces blocs pour ajouter d'autres projets -->
          <article class="card" data-title="Campagne Social — Story Ads" data-img="https://images.unsplash.com/photo-1498050108023-c5249f4df085?q=80&w=1600&auto=format&fit=crop" data-desc="Création de visuels courts et stories optimisées pour Facebook & WhatsApp." data-tags="Social, Visuels">
            <div class="card-img">Preview projet 4</div>
            <h3>Campagne Social — Story Ads</h3>
            <p>Visuels courts et templates réutilisables.</p>
            <div class="meta">
              <span>Ads</span>
              <button onclick="openProjectCard(this)" style="background:transparent;border:0;color:var(--accent2);cursor:pointer;font-weight:600">Voir</button>
            </div>
          </article>

          <article class="card" data-title="Prototype App — Onboarding" data-img="https://images.unsplash.com/photo-1505238680356-667803448bb6?q=80&w=1600&auto=format&fit=crop" data-desc="Prototype animé d'onboarding pour une app éducative." data-tags="Prototype, Animation">
            <div class="card-img">Preview projet 5</div>
            <h3>Prototype App — Onboarding</h3>
            <p>Flow d'accueil & première conversion.</p>
            <div class="meta">
              <span>Prototype</span>
              <button onclick="openProjectCard(this)" style="background:transparent;border:0;color:var(--accent2);cursor:pointer;font-weight:600">Voir</button>
            </div>
          </article>

          <article class="card" data-title="Icon Set — UI Kit" data-img="https://images.unsplash.com/photo-1498050108023-c5249f4df085?q=80&w=1600&auto=format&fit=crop" data-desc="Pack d'icônes et composants pour accélérer le design mobile." data-tags="UI Kit, Assets">
            <div class="card-img">Preview projet 6</div>
            <h3>Icon Set — UI Kit</h3>
            <p>Collection d'assets réutilisables pour apps mobiles.</p>
            <div class="meta">
              <span>Assets</span>
              <button onclick="openProjectCard(this)" style="background:transparent;border:0;color:var(--accent2);cursor:pointer;font-weight:600">Voir</button>
            </div>
          </article>
        </div>
      </section>

      <!-- Modal -->
      <div class="modal" id="projectModal" role="dialog" aria-hidden="true">
        <div class="modal-card">
          <div class="modal-header">
            <div>
              <strong id="modalTitle">Titre Projet</strong>
              <div id="modalTags" style="color:var(--muted);font-size:13px;margin-top:6px"></div>
            </div>
            <button class="close-btn" onclick="closeModal()">✕</button>
          </div>
          <div style="display:flex;gap:16px;flex-wrap:wrap">
            <div style="flex:1;min-width:260px">
              <div id="modalImg" style="height:320px;border-radius:10px;background:#071022;display:flex;align-items:center;justify-content:center;color:var(--muted);overflow:hidden">
                <img id="modalImageElement" src="" alt="" style="width:100%;height:100%;object-fit:cover">
              </div>
            </div>
            <div style="flex:1;min-width:260px">
              <p id="modalDesc" style="color:var(--muted);margin-bottom:10px"></p>
              <div style="margin-top:12px">
                <a id="modalLink" href="#" style="padding:8px 12px;border-radius:10px;background:linear-gradient(90deg,var(--accent1),var(--accent2));color:#fff;display:inline-block">Voir le projet</a>
                <a href="#contact" style="margin-left:10px;padding:8px 12px;border-radius:10px;background:transparent;border:1px solid rgba(255,255,255,0.04);color:var(--muted);display:inline-block">Me contacter</a>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- CONTACT -->
      <section id="contact" aria-label="Contact">
        <div class="section-title">
          <h2>Contact</h2>
          <p>Discutons de ton projet</p>
        </div>

        <div class="contact-grid">
          <form class="card" onsubmit="sendMail(event)">
            <div class="field">
              <label style="color:var(--muted);font-size:13px">Nom</label>
              <input id="name" required placeholder="Ton nom" />
            </div>
            <div class="field">
              <label style="color:var(--muted);font-size:13px">Email</label>
              <input id="email" type="email" required placeholder="exemple@mail.com" />
            </div>
            <div class="field">
              <label style="color:var(--muted);font-size:13px">Projet</label>
              <select id="service">
                <option>Design d'application</option>
                <option>Branding & logo</option>
                <option>Templates pour réseaux</option>
                <option>Autre</option>
              </select>
            </div>
            <div class="field">
              <label style="color:var(--muted);font-size:13px">Message</label>
              <textarea id="message" placeholder="Parle-moi de ton projet..." required></textarea>
            </div>
            <div style="display:flex;gap:10px;align-items:center;justify-content:flex-end">
              <button type="submit" class="btn-primary">Envoyer</button>
            </div>
          </form>

          <aside style="position:relative">
            <div class="card">
              <h3>Infos</h3>
              <p style="color:var(--muted);margin-bottom:10px">Disponible pour missions freelance et collaborations. Réponse sous 48h.</p>
              <div style="margin-top:8px">
                <div class="chip">Email: samuel@example.com</div>
                <div class="chip">WhatsApp: +229 97 XX XX XX</div>
                <div class="chip">Benin — Cotonou</div>
              </div>
              <div style="margin-top:12px">
                <h4 style="color:#fff;margin-bottom:8px">Réseaux</h4>
                <div class="socials">
                  <a class="chip" href="#" target="_blank">Behance</a>
                  <a class="chip" href="#" target="_blank">Dribbble</a>
                  <a class="chip" href="#" target="_blank">LinkedIn</a>
                </div>
              </div>
            </div>

            <div style="margin-top:12px" class="card">
              <h3>Services & Tarifs</h3>
              <p style="color:var(--muted)">Pack starter — Landing simple<br/>Pack pro — App complète<br/>Pack brand — Logo + identité</p>
            </div>
          </aside>
        </div>

      </section>

      <footer>
        <div style="display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:12px">
          <div>© <strong>Samuel Design</strong> — Tous droits réservés</div>
          <div style="color:var(--muted)">Conçu avec ❤️ · Portfolio statique</div>
        </div>
      </footer>
    </main>
  </div>

  <script>
    // Ouvrir modal avec les données du projet (prise depuis l'article parent)
    function openProjectCard(btn){
      // trouve la carte par rapport au bouton
      const card = btn.closest('.card');
      const title = card.dataset.title || card.querySelector('h3').innerText;
      const img = card.dataset.img || '';
      const desc = card.dataset.desc || card.querySelector('p')?.innerText || '';
      const tags = card.dataset.tags || '';

      document.getElementById('modalTitle').innerText = title;
      document.getElementById('modalDesc').innerText = desc;
      document.getElementById('modalTags').innerText = tags;
      const imgEl = document.getElementById('modalImageElement');
      if(img){
        imgEl.src = img;
        imgEl.alt = title;
        imgEl.style.display = 'block';
      } else {
        imgEl.style.display = 'none';
      }
      document.getElementById('modalLink').href = '#'; // si tu as une page projet, mets ici l'URL
      document.getElementById('projectModal').classList.add('open');
      document.getElementById('projectModal').setAttribute('aria-hidden','false');
    }

    function closeModal(){
      document.getElementById('projectModal').classList.remove('open');
      document.getElementById('projectModal').setAttribute('aria-hidden','true');
    }

    // Fermer modal au clic hors carte
    document.getElementById('projectModal').addEventListener('click', function(e){
      if(e.target === this) closeModal();
    });

    // Formulaire: ouvre le mail client via mailto (simple)
    function sendMail(e){
      e.preventDefault();
      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();
      const service = document.getElementById('service').value;
      const message = document.getElem
