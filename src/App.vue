<template>
  <div>
    <Navbar />
    <About />
    <h1 class="text-3xl font-semibold mx-8">print('My Projects')</h1>
    <div class="grid grid-cols-2 gap-4 p-4">
      <PortfolioCard v-for="project in fetchedProjects" :key="project.id" :project="project"/>
    </div>
    <Footer />
  </div>
</template>

<script>
import PortfolioCard from './components/PortfolioCard.vue';
import Navbar from './components/Navbar.vue';
import About from './components/About.vue';
import Footer from './components/Footer.vue';

import axios from 'axios';

export default {
  components: {
    PortfolioCard,
    Navbar,
    About,
    Footer
  },
  data() {
    return {
      fetchedProjects: []
    };
  },
  created() {
    this.fetchGitHubProjects();
  },
  methods: {
    async fetchGitHubProjects() {
      try {
        const response = await axios.get('https://api.github.com/users/edypnog/repos');
        this.fetchedProjects = response.data.map(repo => ({
          id: repo.id,
          title: repo.name,
          description: repo.description,
          link: repo.html_url,
          language: repo.language
        }));
      } catch (error) {
        console.error('Error fetching GitHub projects:', error);
      }
    }
  }
};
</script>

<style scoped>
/* Dark theme */
.bg-gray-900 {
  background-color: #1a202c;
}

.text-white {
  color: #ffffff;
}

.text-gray-300 {
  color: #cbd5e0;
}

.text-blue-500 {
  color: #4299e1;
}

/* Additional styling */
.shadow-md {
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
}

.hover\:underline:hover {
  text-decoration: underline;
}
</style>