<script setup>
import { useRouter } from 'vue-router'; 
import TopBar from '@/components/topBar.vue'; 
import GetStartedButton from '@/components/getStartedButton.vue'; 
import { Home as HomeIcon, Info as InfoIcon, Languages as LanguagesIcon, Settings as SettingsIcon } from 'lucide-vue-next'; 
import Footer from '@/components/Footer.vue'; 

const router = useRouter();

const navigationItems = [
    { name: 'Accueil', path: '/', icon: HomeIcon }, 
    { name: 'À Propos', path: '/about', icon: InfoIcon },
    { name: 'Traducteur', path: '/translator', icon: LanguagesIcon },
    { name: 'Paramètres', path: '/settings', icon: SettingsIcon }
];

const handleLogoClick = () => {
    router.push('/'); 
};

const handleNavClick = (item) => {
    console.log('Nav item clicked:', item.name);
};

const handleGetStarted = () => {
    router.push('/translator'); 
};
</script>

<template>
  <div>
    <TopBar
      :nav-items="navigationItems"
      variant="blur"
      position="sticky"
      :shrink-on-scroll="true"
      @logo-click="handleLogoClick"
      @nav-item-click="handleNavClick"
    />

    <!-- SECTION HERO -->
    <section class="hero">
      <div class="hero-content">
        <h1 class="hero-title">
          La parole qui voyage. <br>
          <span class="highlight">La culture qui vit.</span>
        </h1>
        <p class="hero-subtitle">
          Traduisez et écoutez vos textes en langues locales africaines : <br>
          <strong>Bété, Baoulé, Mooré, Agni.</strong>
        </p>
        <GetStartedButton variant="primary" size="lg" @click="handleGetStarted">
          Commencer la traduction
        </GetStartedButton>
      </div>
    </section>

    <!-- SECTION AVANTAGES / FONCTIONNALITÉS -->
    <section class="features">
      <h2>Pourquoi utiliser Kumajala ?</h2>
      <div class="features-grid">
        <div class="feature-card">
          <div class="icon-wrapper">🌍</div>
          <h3>Traduction Intelligente</h3>
          <p>Traduisez instantanément du français vers plusieurs langues locales avec précision.</p>
        </div>
        <div class="feature-card">
          <div class="icon-wrapper">🔊</div>
          <h3>Synthèse Vocale</h3>
          <p>Écoutez la prononciation de vos traductions pour mieux apprendre et communiquer.</p>
        </div>
        <div class="feature-card">
          <div class="icon-wrapper">🛡️</div>
          <h3>Patrimoine Culturel</h3>
          <p>Participez à la préservation et à la valorisation de nos langues maternelles.</p>
        </div>
      </div>
    </section>
    <Footer />
  </div>
</template>

<style scoped>
/* --- HERO --- */
.hero {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 120px 20px;
  background: linear-gradient(135deg, var(--cl-gray-100) 0%, #e0e7ff 100%); /* Légère teinte bleutée pour la modernité */
  min-height: calc(100vh - 80px); 
}

.hero-content {
  max-width: 800px;
}

.hero-title {
  font-size: var(--fs-5xl); 
  color: var(--cl-primary);
  margin-bottom: var(--space-6); 
  line-height: 1.2;
  font-weight: 800;
}

.highlight {
  background: linear-gradient(90deg, var(--cl-primary), var(--cl-secondary));
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.hero-subtitle {
  font-size: var(--fs-xl); 
  color: var(--cl-gray-700);
  margin-bottom: var(--space-10); 
  line-height: 1.6;
}

.hero-subtitle strong {
  color: var(--cl-secondary);
}

/* --- FEATURES --- */
.features {
  padding: var(--space-24) var(--space-4); 
  text-align: center;
  background-color: var(--cl-white);
}

.features h2 {
  font-size: var(--fs-4xl); 
  margin-bottom: var(--space-16); 
  color: var(--cl-primary); 
  font-weight: 700;
}

.features-grid {
  display: grid;
  gap: var(--space-8); 
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  max-width: 1100px; 
  margin: 0 auto;
}

.feature-card {
  background: var(--cl-white);
  padding: var(--space-10); 
  border-radius: var(--radius-xl); 
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
  transition: all 0.3s ease;
  border: 1px solid var(--cl-gray-200);
}

.feature-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
  border-color: var(--cl-primary-light);
}

.icon-wrapper {
  font-size: 3rem;
  margin-bottom: var(--space-6);
}

.feature-card h3 {
  color: var(--cl-primary);
  margin-bottom: var(--space-4); 
  font-size: var(--fs-xl);
  font-weight: 600;
}

.feature-card p {
  color: var(--cl-gray-600); 
  line-height: 1.6;
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .hero {
    padding: 80px 20px;
    min-height: auto;
  }
  .hero-title {
    font-size: var(--fs-4xl);
  }
  .hero-subtitle {
    font-size: var(--fs-lg);
  }
  .features {
    padding: 60px 20px;
  }
}
</style>
