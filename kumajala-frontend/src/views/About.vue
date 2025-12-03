<script setup>
import EnhancedHeader from '@/components/topBar.vue';
import { Home as HomeIcon, Info as InfoIcon, Languages as LanguagesIcon, Settings as SettingsIcon } from 'lucide-vue-next'; 
import Footer from '@/components/Footer.vue'; 
const navigationItems = [
    { name: 'Accueil', path: '/', icon: HomeIcon }, 
    { name: 'À Propos', path: '/about', icon: InfoIcon },
    { name: 'Traducteur', path: '/translator', icon: LanguagesIcon },
    { name: 'Paramètres', path: '/settings', icon: SettingsIcon }
];

const handleLogoClick = () => {
    console.log('Logo clicked!');
};

const handleNavClick = (item) => {
    console.log('Nav item clicked:', item.name);
};
</script>

<template>
  <div>
    <EnhancedHeader
      :nav-items="navigationItems"
      variant="blur"
      position="sticky"
      :shrink-on-scroll="true"
      @logo-click="handleLogoClick"
      @nav-item-click="handleNavClick"
    />

    <!-- SECTION ABOUT -->
    <section class="about-hero">
      <div class="hero-content">
        <h1>À propos de <span class="highlight">Kumajala</span></h1>
        <p>Une initiative pour valoriser les langues africaines dans le numérique en combinant intelligence artificielle et tradition.</p>
      </div>
    </section>

    <section class="about-content">
      <div class="mission-vision-grid">
        <div class="content-block">
          <h2>Notre Mission</h2>
          <p>
            Chez Kumajala, nous croyons que la technologie doit servir la culture. Notre mission est de briser les barrières linguistiques en rendant la traduction des langues locales africaines (Bété, Baoulé, Mooré, Agni) accessible à tous, instantanément.
          </p>
        </div>

        <div class="content-block">
          <h2>Notre Vision</h2>
          <p>
            Nous imaginons un monde où nos langues maternelles ne sont pas seulement parlées au village, mais vivent pleinement dans l'espace numérique. Kumajala se veut être ce pont numérique entre les générations et les cultures.
          </p>
        </div>
      </div>

      <div class="values-section">
        <h2>Nos Valeurs</h2>
        <div class="values-grid">
          <div class="value-item">
            <span class="value-icon">🌿</span>
            <h3>Préservation Culturelle</h3>
            <p>Sauvegarder notre héritage linguistique pour les générations futures.</p>
          </div>
          <div class="value-item">
            <span class="value-icon">💡</span>
            <h3>Innovation Utile</h3>
            <p>Utiliser l'IA pour résoudre des problèmes concrets d'accessibilité.</p>
          </div>
          <div class="value-item">
            <span class="value-icon">🤝</span>
            <h3>Accessibilité</h3>
            <p>Une technologie simple et ouverte à tous, sans barrière technique.</p>
          </div>
        </div>
      </div>
    </section>

    <Footer />
  </div>
</template>

<style scoped>
.about-hero {
  padding: 120px 20px;
  text-align: center;
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
  min-height: 400px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero-content {
  max-width: 800px;
}

.about-hero h1 {
  font-size: 3rem;
  color: var(--cl-primary);
  margin-bottom: 1.5rem;
  font-weight: 800;
}

.about-hero .highlight {
  background: linear-gradient(90deg, var(--cl-primary), var(--cl-secondary));
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.about-hero p {
  font-size: 1.25rem;
  color: var(--cl-gray-700);
  line-height: 1.6;
}

.about-content {
  max-width: 1000px;
  margin: 0 auto;
  padding: 80px 20px;
}

.mission-vision-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  margin-bottom: 6rem;
}

.content-block h2 {
  font-size: 2rem;
  color: var(--cl-primary);
  margin-bottom: 1.5rem;
  position: relative;
  display: inline-block;
}

.content-block h2::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 0;
  width: 60px;
  height: 4px;
  background: var(--cl-secondary);
  border-radius: 2px;
}

.content-block p {
  font-size: 1.1rem;
  line-height: 1.8;
  color: var(--cl-gray-700);
}

.values-section {
  text-align: center;
}

.values-section h2 {
  font-size: 2.5rem;
  color: var(--cl-primary);
  margin-bottom: 3rem;
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.value-item {
  background: white;
  padding: 2rem;
  border-radius: 1rem;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.value-item:hover {
  transform: translateY(-5px);
}

.value-icon {
  font-size: 3rem;
  display: block;
  margin-bottom: 1rem;
}

.value-item h3 {
  color: var(--cl-primary);
  margin-bottom: 1rem;
  font-size: 1.25rem;
}

.value-item p {
  color: var(--cl-gray-600);
  line-height: 1.6;
}

@media (max-width: 768px) {
  .mission-vision-grid {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
  
  .about-hero h1 {
    font-size: 2.5rem;
  }
}
</style>
