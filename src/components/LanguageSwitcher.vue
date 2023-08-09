<template>
    <div>
      <button @click="toggleLanguage">
        {{ currentLanguage === 'en' ? 'Português' : 'English' }}
      </button>
    </div>
</template>
  
<script>
  export default {
    data() {
      return {
        currentLanguage: 'en', // Default language is English
        translations: {}
      };
    },
    created() {
      this.loadTranslations();
    },
    methods: {
      async loadTranslations() {
        const response = await import(`../translations/${this.currentLanguage}.json`);
        this.translations = response.default;
      },
      toggleLanguage() {
        this.currentLanguage = this.currentLanguage === 'en' ? 'pt' : 'en';
        this.loadTranslations();
      }
    }
  };
</script>
  