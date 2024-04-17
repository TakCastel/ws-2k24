<template>
  <div class="font-sans bg-gradient-to-b from-slate-950 via-indigo-950 to-slate-950 text-white">
    <!-- Header -->
    <header class="py-6 px-8 bg-black">
      <h1 class="text-white text-3xl font-semibold">Mon Portfolio</h1>
    </header>

    <section class="relative h-screen bg-cover bg-center" style="background-image: url('images/jumbotron.png'); filter: opacity(0.8);">
      <div class="container mx-auto px-4 md:px-0 h-full flex items-center justify-center">
        <div class="text-center text-white">
          <h2 class="text-4xl font-semibold mb-4">
            À propos de moi
          </h2>
          <p class="text-lg">
            Développeur spécialisé en Vue.js, axé sur le développement d'applications métier et le design UX. Mon expertise vise à créer des solutions web intuitives et efficaces, tout en contribuant à la transformation digitale des entreprises.
          </p>
        </div>
      </div>
    </section>


    <!-- Portfolio -->
    <section id="portfolio" class="container mx-auto px-4 md:px-0 py-12">
      <h2 class="text-2xl font-semibold mb-4">
        Portfolio
      </h2>

      <!-- Cartes des projets -->
      <div class="grid grid-cols-2 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
        <!-- Utilisation de v-for pour créer dynamiquement les cartes -->
        <div 
          v-for="(item, index) in projects" 
          :key="index" 
          class="flex flex-col relative group bg-slate-950 rounded-lg overflow-hidden shadow-md hover:scale-105 hover:shadow-xl hover:bg-gradient-to-r hover:from-fuchsia-900 hover:to-fuchsia-950 transition duration-300 ease-in-out"
        >          
          <!-- Image (si présente) -->
          <img 
            v-if="item.image" 
            :src="item.image" 
            :alt="item.title" 
            class="w-full h-48 object-cover z-20" 
          />

          <div class="p-4 pb-0">
            <!-- Titre -->
            <h3 class="text-xl font-semibold mb-2 text-white transition duration-120 ease-in-out z-20">{{ item.title }}</h3>
            <!-- Description -->
            <p class="text-slate-500 mb-4 z-20 group-hover:text-slate-300 transition duration-120 ease-in-out">{{ item.description }}</p>
            <!-- Lien -->
          </div>

          <a :href="item.link" target="_blank" class="p-4 pt-0 text-amber-400 underline mt-auto">Voir plus</a>
        </div>
      </div>
    </section>

  <!-- Description des services -->
    <section class="container mx-auto px-4 md:px-0 py-12">
      <!-- Développement Frontend -->
      <div class="flex flex-col md:flex-row md:items-center mb-8">
        <!-- Image à gauche pour desktop -->
        <!-- <div class="md:w-1/4 mb-4 md:mb-0 md:mr-4">
          <img src="/path/to/dev-icon.png" alt="Développement Frontend" class="w-full h-auto md:hidden">
          <img src="/path/to/dev-image.png" alt="Développement Frontend" class="w-full h-auto hidden md:block">
        </div> -->
        <!-- Texte -->
        <div class="md:w-3/4">
          <h3 class="text-xl font-semibold mb-2">Développement Frontend</h3>
          <p class="text-gray-600">
            Fort d'une expertise solide en HTML, CSS et JavaScript, je conçois des interfaces web modernes et réactives qui captivent et engagent les utilisateurs.
          </p>
        </div>
      </div>

      <!-- Conception UI/UX -->
      <div class="flex flex-col md:flex-row-reverse md:items-center mb-8">
        <!-- Image à droite pour desktop -->
        <!-- <div class="md:w-1/4 mb-4 md:mb-0 md:ml-4">
          <img src="/images/uiux-icon.png" alt="Conception UI/UX" class="w-full h-auto md:hidden">
          <img src="/images/uiux-image.png" alt="Conception UI/UX" class="w-full h-auto hidden md:block">
        </div> -->
        <!-- Texte -->
        <div class="md:w-3/4">
          <h3 class="text-xl font-semibold mb-2">Conception UI/UX</h3>
          <p class="text-gray-600">
            Passionné par le design et l'expérience utilisateur, je mets un point d'honneur à créer des interfaces intuitives et esthétiques qui optimisent la satisfaction et la fidélisation des utilisateurs.
          </p>
        </div>
      </div>

      <!-- Gestion de Projet -->
      <div class="flex flex-col md:flex-row md:items-center">
        <!-- Image à gauche pour desktop -->
        <!-- <div class="md:w-1/4 mb-4 md:mb-0 md:mr-4">
          <img src="/images/project-icon.png" alt="Gestion de Projet" class="w-full h-auto md:hidden">
          <img src="/images/project-image.png" alt="Gestion de Projet" class="w-full h-auto hidden md:block">
        </div> -->
        <!-- Texte -->
        <div class="md:w-3/4">
          <h3 class="text-xl font-semibold mb-2">Gestion de Projet</h3>
          <p class="text-gray-600">
            Avec une approche méthodique et organisée, je coordonne efficacement les équipes et les ressources pour garantir la livraison de projets de qualité, dans les délais et en respectant les objectifs fixés.
          </p>
        </div>
      </div>

    </section>

    <!-- Contact -->
    <section class="container mx-auto px-4 md:px-0 py-12">
      <h2 class="text-2xl font-semibold mb-4">
        Contact
      </h2>
      <!-- Formulaire de contact à ajouter ici -->
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "Archéode",
          description: "Maintenance du site d'une guilde RP hébergé sur Ghost en tant que GM et créateur de contenu",
          image: "images/portfolio-archeode.png",
          link: "https://www.archeode.fr/"
        },
        {
          title: "Proréno",
          description: "Mise en place de l'architecture de fichiers et composants frontend, et intégration de la liseuse PDF du site Proréno chez Gingerminds",
          image: "images/portfolio-proreno.png",
          link: "https://www.proreno.fr/"
        },
        {
          title: "Klosup",
          description: "Intégration frontend des pages et du panier d'achat sur Klosup chez Gingerminds",
          image: "images/portfolio-klosup.png",
          link: "https://www.klosup.fr/"
        },
        {
          title: "Yes Stockmeier",
          description: "Développement de l'application scan de documents et dashboard interne de Yes Stockmeier chez Gingerminds",
          image: "images/portfolio-yes.png",
          link: "https://yes.stockmeier.fr/fr/connexion/"
        },
        {
          title: "Jungloo",
          description: "Mise en place de l'architecture frontend des composants UI pour le design system de l'application Jungloo chez Motion4ever",
          image: "images/portfolio-jungloo.png",
          link: "https://app.jungloo.fr/register"
        },
        {
          title: "Fiscapass",
          description: "Développement de l'application web de conformité fiscale pour Fiscapass chez Motion4ever",
          image: "images/portfolio-fiscapass.png",
          link: "https://www.fisca-pass.fr/"
        },
        {
          title: "Mes Arbustes",
          description: "Site e-commerce Prestashop pour la pépinière MesArbustes, en tant que développeur frontend chez Motion4ever",
          image: "images/portfolio-mesarbustes.png",
          link: "https://www.mesarbustes.fr/"
        },
        {
          title: "Bubblecast",
          description: "Réalisation d'une application de lecture de podcasts chez Mediameeting",
          image: "images/portfolio-mediameeting.png",
          link: "https://www.mediameeting.fr/"
        },
        // {
        //   title: "Mybeautyfullradio",
        //   description: "Développement de l'application web Mybeautyfullradio en tant que développeur à Mediameeting",
        //   image: "images/portfolio-wella.png",
        //   link: "https://www.mediameeting.fr/portfolio/wella-mybeautyfullradio/"
        // },
        // {
        //   title: "Gamestory",
        //   description: "Mini-jeu dont vous êtes le héros, réalisé en React en 2017 pour apprendre le langage",
        //   image: "images/portfolio-gamestory.png",
        //   link: "https://takcastel.github.io/gamestory/"
        // },
        // {
        //   title: "SWOR",
        //   description: "Création d'un forum et scénariste pour une communauté de rôlistes sur Star Wars en 2013",
        //   image: "images/portfolio-swor.png",
        //   link: "http://www.swor-jdr.com/"
        // },
      ]
    };
  }
};
</script>