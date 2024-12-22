<template>
  <Header :themes="themes" />

  <AllThemes :themes="themes" />

  <MainArticles />
</template>

<script>
import Header from './Header.vue'
import AllThemes from './AllThemes.vue'
import MainArticles from './MainArticles.vue'

export default {
  components: {
    Header,
    AllThemes,
    MainArticles,
  },

  data() {
    return {
      themes: [
        'Tutti i temi',
        'Ambiente',
        'Economia',
        'Mondo',
        'Non profit',
        'Politica',
        'Società',
        'Welfare',
      ],
    }
  },
}
</script>

<style scoped></style>
