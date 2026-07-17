<template>
  <div class="app">
    <aside class="ad-sidebar" aria-label="Publicidade">
      <div class="ad-container">
        <ins class="adsbygoogle"
          style="display:block"
          data-ad-client="ca-pub-4795950358148786"
          data-ad-slot="5489194033"
          data-ad-format="auto"
          data-full-width-responsive="true"></ins>
      </div>
      <span class="ad-label">pub</span>
    </aside>

    <header class="header">
      <div class="header-content">
        <div class="logo-area">
          <img src="/logo.png" alt="E.M.E" class="logo" />
          <div class="brand">
            <h1 class="brand-name">Expor <span class="gold">EME</span> Company</h1>
            <p class="brand-tagline">Inovação em gaming</p>
          </div>
        </div>
        <nav class="nav">
          <a href="#apps" class="nav-link">Apps</a>
          <a href="#about" class="nav-link">Sobre</a>
          <a href="https://github.com/Eriklebson" target="_blank" class="nav-link">GitHub</a>
        </nav>
      </div>
    </header>

    <section class="hero">
      <div class="hero-bg"></div>
      <div class="hero-content">
        <img src="/logo.png" alt="E.M.E Core" class="hero-logo" />
        <h2 class="hero-title">
          E.M.E <span class="gold">Core</span>
        </h2>
        <p class="hero-desc">
          Launcher de jogos desktop nativo para Windows — organize, descubra e jogue seus jogos favoritos.
        </p>
        <div class="hero-badges">
          <span class="badge badge-blue">WinUI 3</span>
          <span class="badge badge-purple">.NET 8.0</span>
          <span class="badge badge-gold">100% Offline</span>
        </div>
        <div class="hero-actions">
          <a
            v-if="latestRelease"
            :href="downloadUrl"
            class="btn btn-primary"
            target="_blank"
          >
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4" />
              <polyline points="7 10 12 15 17 10" />
              <line x1="12" y1="15" x2="12" y2="3" />
            </svg>
            Download v{{ latestVersion }}
          </a>
          <a
            v-else
            href="https://github.com/Eriklebson/EMECore/releases"
            class="btn btn-primary"
            target="_blank"
          >
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4" />
              <polyline points="7 10 12 15 17 10" />
              <line x1="12" y1="15" x2="12" y2="3" />
            </svg>
            Download
          </a>
          <a
            href="https://github.com/Eriklebson/EMECore"
            class="btn btn-secondary"
            target="_blank"
          >
            Ver no GitHub
          </a>
        </div>
        <p v-if="latestRelease" class="release-date">
          Último release: {{ formatDate(latestRelease.published_at) }}
        </p>
      </div>
    </section>

    <section id="apps" class="section">
      <div class="section-content">
        <h2 class="section-title">
          Nossos <span class="gold">Apps</span>
        </h2>
        <p class="section-subtitle">Aplicativos desenvolvidos pela E.M.E Company</p>

        <div class="apps-grid">
          <div class="app-card">
            <div class="app-icon">
              <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="var(--gold)" stroke-width="1.5">
                <rect x="2" y="3" width="20" height="14" rx="2" ry="2" />
                <line x1="8" y1="21" x2="16" y2="21" />
                <line x1="12" y1="17" x2="12" y2="21" />
              </svg>
            </div>
            <h3 class="app-name">E.M.E Core</h3>
            <p class="app-desc">Launcher de jogos desktop com scanner automático, biblioteca visual, monitor de hardware e conquistas.</p>
            <div class="app-features">
              <span class="feature">Scanner Steam/Xbox</span>
              <span class="feature">Monitor HW</span>
              <span class="feature">Conquistas</span>
              <span class="feature">Capas Auto</span>
            </div>
            <div class="app-status">
              <span class="status-badge status-live">Disponível</span>
              <span class="app-version" v-if="latestVersion">v{{ latestVersion }}</span>
            </div>
            <a
              v-if="latestRelease"
              :href="downloadUrl"
              class="btn btn-card"
              target="_blank"
            >
              Download
            </a>
            <a
              v-else
              href="https://github.com/Eriklebson/EMECore/releases"
              class="btn btn-card"
              target="_blank"
            >
              Download
            </a>
          </div>

          <div class="app-card app-card-soon">
            <div class="app-icon">
              <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="var(--purple)" stroke-width="1.5">
                <path d="M12 2L2 7l10 5 10-5-10-5z" />
                <path d="M2 17l10 5 10-5" />
                <path d="M2 12l10 5 10-5" />
              </svg>
            </div>
            <h3 class="app-name">EME Platform</h3>
            <p class="app-desc">Plataforma integrada para gerenciamento de jogos e comunidade. Em desenvolvimento.</p>
            <div class="app-status">
              <span class="status-badge status-soon">Em breve</span>
            </div>
            <button class="btn btn-card btn-disabled" disabled>Em breve</button>
          </div>
        </div>
      </div>
    </section>

    <section id="about" class="section section-alt">
      <div class="section-content">
        <h2 class="section-title">
          Sobre a <span class="gold">E.M.E</span> Company
        </h2>
        <div class="about-grid">
          <div class="about-card">
            <div class="about-icon gold">
              <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                <polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2" />
              </svg>
            </div>
            <h3>Qualidade</h3>
            <p>Aplicativos nativos Windows com performance e experiência premium.</p>
          </div>
          <div class="about-card">
            <div class="about-icon blue">
              <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                <rect x="3" y="11" width="18" height="11" rx="2" ry="2" />
                <path d="M7 11V7a5 5 0 0 1 10 0v4" />
              </svg>
            </div>
            <h3>Privacidade</h3>
            <p>100% offline. Seus dados ficam no seu PC, sem coleta de dados.</p>
          </div>
          <div class="about-card">
            <div class="about-icon purple">
              <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
                <path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z" />
              </svg>
            </div>
            <h3>Performance</h3>
            <p>C# WinUI 3 nativo, baixo consumo de RAM e CPU.</p>
          </div>
        </div>
      </div>
    </section>

    <footer class="footer">
      <div class="footer-content">
        <div class="footer-logo">
          <img src="/logo.png" alt="E.M.E" class="footer-logo-img" />
          <span class="footer-brand">E.M.E Company</span>
        </div>
        <div class="footer-links">
          <a href="https://github.com/Eriklebson/EMECore" target="_blank">GitHub</a>
          <a href="https://github.com/Eriklebson" target="_blank">Autor</a>
          <a href="/EMECorePage/privacy.html">Privacidade</a>
          <a href="/EMECorePage/terms.html">Termos</a>
        </div>
        <p class="footer-copy">&copy; 2026 E.M.E Company. Todos os direitos reservados.</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      latestRelease: null,
      latestVersion: null,
    }
  },
  computed: {
    downloadUrl() {
      if (!this.latestRelease) return '#'
      const asset = this.latestRelease.assets?.find(a =>
        a.name.endsWith('.exe') || a.name.endsWith('.zip') || a.name.endsWith('.msix')
      )
      return asset ? asset.browser_download_url : this.latestRelease.html_url
    },
  },
  mounted() {
    this.fetchLatestRelease()
  },
  methods: {
    async fetchLatestRelease() {
      try {
        const response = await fetch(
          'https://api.github.com/repos/Eriklebson/EMECore/releases/latest'
        )
        if (response.ok) {
          this.latestRelease = await response.json()
          this.latestVersion = this.latestRelease.tag_name?.replace(/^v/, '') || ''
        }
      } catch (e) {
        console.warn('Não foi possível buscar releases:', e)
      }
    },
    formatDate(dateStr) {
      if (!dateStr) return ''
      return new Date(dateStr).toLocaleDateString('pt-BR', {
        day: '2-digit',
        month: 'long',
        year: 'numeric',
      })
    },
  },
}
</script>

<style scoped>
.gold {
  color: var(--gold);
}

/* Header */
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  background: rgba(10, 10, 18, 0.9);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--border-color);
}

.header-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0.75rem 2rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo-area {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.logo {
  width: 40px;
  height: 40px;
  border-radius: 8px;
  object-fit: contain;
}

.brand-name {
  font-size: 1.1rem;
  font-weight: 700;
  letter-spacing: 0.5px;
}

.brand-tagline {
  font-size: 0.7rem;
  color: var(--text-secondary);
  text-transform: uppercase;
  letter-spacing: 1.5px;
}

.nav {
  display: flex;
  gap: 2rem;
}

.nav-link {
  font-size: 0.85rem;
  font-weight: 500;
  color: var(--text-secondary);
  transition: color 0.2s;
}

.nav-link:hover {
  color: var(--gold);
}

/* Hero */
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 6rem 2rem 4rem;
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse at 20% 50%, rgba(45, 125, 210, 0.12) 0%, transparent 50%),
    radial-gradient(ellipse at 80% 50%, rgba(123, 63, 160, 0.12) 0%, transparent 50%),
    radial-gradient(ellipse at 50% 0%, rgba(201, 162, 39, 0.08) 0%, transparent 40%);
  pointer-events: none;
}

.hero-content {
  position: relative;
  max-width: 700px;
}

.hero-logo {
  width: 160px;
  height: 160px;
  margin-bottom: 1.5rem;
  border-radius: 20px;
  filter: drop-shadow(0 0 40px rgba(201, 162, 39, 0.3));
  animation: float 4s ease-in-out infinite;
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 900;
  letter-spacing: -1px;
  margin-bottom: 1rem;
}

.hero-desc {
  font-size: 1.15rem;
  color: var(--text-secondary);
  margin-bottom: 1.5rem;
  max-width: 500px;
  margin-left: auto;
  margin-right: auto;
}

.hero-badges {
  display: flex;
  gap: 0.5rem;
  justify-content: center;
  margin-bottom: 2rem;
  flex-wrap: wrap;
}

.badge {
  padding: 0.35rem 0.85rem;
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.badge-gold {
  background: rgba(201, 162, 39, 0.15);
  color: var(--gold);
  border: 1px solid rgba(201, 162, 39, 0.3);
}

.badge-blue {
  background: rgba(45, 125, 210, 0.15);
  color: var(--blue-light);
  border: 1px solid rgba(45, 125, 210, 0.3);
}

.badge-purple {
  background: rgba(123, 63, 160, 0.15);
  color: var(--purple-light);
  border: 1px solid rgba(123, 63, 160, 0.3);
}

.hero-actions {
  display: flex;
  gap: 1rem;
  justify-content: center;
  margin-bottom: 1rem;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.8rem 1.5rem;
  border-radius: 10px;
  font-size: 0.9rem;
  font-weight: 600;
  transition: all 0.25s ease;
}

.btn-primary {
  background: linear-gradient(135deg, var(--gold), var(--gold-dark));
  color: #0a0a12;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(201, 162, 39, 0.35);
}

.btn-secondary {
  background: transparent;
  color: var(--text-primary);
  border: 1px solid var(--border-color);
}

.btn-secondary:hover {
  border-color: var(--gold);
  color: var(--gold);
}

.release-date {
  font-size: 0.8rem;
  color: var(--text-secondary);
}

/* Sections */
.section {
  padding: 5rem 2rem;
}

.section-alt {
  background: var(--bg-card);
}

.section-content {
  max-width: 1100px;
  margin: 0 auto;
}

.section-title {
  font-size: 2.2rem;
  font-weight: 800;
  text-align: center;
  margin-bottom: 0.5rem;
}

.section-subtitle {
  text-align: center;
  color: var(--text-secondary);
  margin-bottom: 3rem;
  font-size: 1rem;
}

/* Apps Grid */
.apps-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 1.5rem;
}

.app-card {
  background: var(--bg-dark);
  border: 1px solid var(--border-color);
  border-radius: 16px;
  padding: 2rem;
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
}

.app-card:hover {
  border-color: var(--gold-dark);
  transform: translateY(-4px);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.4);
}

.app-card-soon {
  opacity: 0.7;
}

.app-card-soon:hover {
  border-color: var(--border-color);
  transform: none;
}

.app-icon {
  width: 64px;
  height: 64px;
  border-radius: 14px;
  background: rgba(201, 162, 39, 0.08);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.25rem;
}

.app-name {
  font-size: 1.3rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
}

.app-desc {
  font-size: 0.9rem;
  color: var(--text-secondary);
  margin-bottom: 1rem;
  line-height: 1.6;
  flex: 1;
}

.app-features {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  margin-bottom: 1rem;
}

.feature {
  padding: 0.25rem 0.6rem;
  border-radius: 6px;
  font-size: 0.7rem;
  font-weight: 600;
  background: rgba(201, 162, 39, 0.1);
  color: var(--gold);
  border: 1px solid rgba(201, 162, 39, 0.2);
}

.app-status {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 1rem;
}

.status-badge {
  padding: 0.25rem 0.7rem;
  border-radius: 20px;
  font-size: 0.7rem;
  font-weight: 600;
}

.status-live {
  background: rgba(34, 197, 94, 0.15);
  color: #22c55e;
}

.status-soon {
  background: rgba(168, 162, 158, 0.15);
  color: #a8a29e;
}

.app-version {
  font-size: 0.8rem;
  color: var(--text-secondary);
  font-weight: 500;
}

.btn-card {
  background: linear-gradient(135deg, var(--gold), var(--gold-dark));
  color: #0a0a12;
  justify-content: center;
  padding: 0.7rem 1.2rem;
  font-size: 0.85rem;
}

.btn-card:hover {
  transform: translateY(-1px);
  box-shadow: 0 6px 20px rgba(201, 162, 39, 0.3);
}

.btn-disabled {
  background: rgba(100, 100, 120, 0.3);
  color: var(--text-secondary);
  cursor: not-allowed;
}

.btn-disabled:hover {
  transform: none;
  box-shadow: none;
}

/* About */
.about-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
}

.about-card {
  background: var(--bg-dark);
  border: 1px solid var(--border-color);
  border-radius: 14px;
  padding: 2rem;
  text-align: center;
  transition: border-color 0.3s;
}

.about-card:hover {
  border-color: var(--gold-dark);
}

.about-icon {
  width: 56px;
  height: 56px;
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1rem;
}

.about-icon.gold {
  background: rgba(201, 162, 39, 0.12);
  color: var(--gold);
}

.about-icon.blue {
  background: rgba(45, 125, 210, 0.12);
  color: var(--blue-light);
}

.about-icon.purple {
  background: rgba(123, 63, 160, 0.12);
  color: var(--purple-light);
}

.about-card h3 {
  font-size: 1.1rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
}

.about-card p {
  font-size: 0.9rem;
  color: var(--text-secondary);
  line-height: 1.6;
}

/* Footer */
.footer {
  border-top: 1px solid var(--border-color);
  padding: 2.5rem 2rem;
  background: var(--bg-dark);
}

.footer-content {
  max-width: 1100px;
  margin: 0 auto;
  text-align: center;
}

.footer-logo {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.6rem;
  margin-bottom: 1rem;
}

.footer-logo-img {
  width: 28px;
  height: 28px;
  border-radius: 6px;
  object-fit: contain;
}

.footer-brand {
  font-weight: 700;
  font-size: 0.95rem;
}

.footer-links {
  display: flex;
  gap: 1.5rem;
  justify-content: center;
  margin-bottom: 1rem;
}

.footer-links a {
  font-size: 0.85rem;
  color: var(--text-secondary);
  transition: color 0.2s;
}

.footer-links a:hover {
  color: var(--gold);
}

.footer-copy {
  font-size: 0.75rem;
  color: var(--text-secondary);
}

/* Ad Sidebar */
.ad-sidebar {
  position: fixed;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
  z-index: 50;
  width: 160px;
  padding: 8px;
  opacity: 0.6;
  transition: opacity 0.3s ease;
}

.ad-sidebar:hover {
  opacity: 1;
}

.ad-container {
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 8px;
  overflow: hidden;
  min-height: 600px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.ad-label {
  display: block;
  text-align: center;
  font-size: 0.55rem;
  color: var(--text-secondary);
  opacity: 0.5;
  margin-top: 4px;
  text-transform: uppercase;
  letter-spacing: 1px;
}

/* Responsive */
@media (max-width: 1100px) {
  .ad-sidebar {
    display: none;
  }
}

@media (max-width: 768px) {
  .header-content {
    padding: 0.75rem 1rem;
  }

  .nav {
    gap: 1rem;
  }

  .nav-link {
    font-size: 0.75rem;
  }

  .hero {
    padding: 5rem 1rem 3rem;
  }

  .hero-logo {
    width: 120px;
    height: 120px;
  }

  .hero-title {
    font-size: 2.2rem;
  }

  .hero-desc {
    font-size: 1rem;
  }

  .hero-actions {
    flex-direction: column;
    align-items: center;
  }

  .section {
    padding: 3rem 1rem;
  }

  .section-title {
    font-size: 1.6rem;
  }

  .apps-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 480px) {
  .brand-tagline {
    display: none;
  }

  .brand-name {
    font-size: 0.95rem;
  }

  .hero-title {
    font-size: 1.8rem;
  }
}
</style>
