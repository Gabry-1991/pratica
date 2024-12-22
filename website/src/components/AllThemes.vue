<template>
  <div class="container">
    <h2 class="title">Tutti i temi</h2>

    <div class="container--buttons">
      <Button
        v-for="(tab, idx) of themes.slice(1)"
        :key="idx"
        :background="getBackground(idx)"
        class="tab"
      >
        <template #content>{{ tab }}</template>
      </Button>
    </div>
  </div>
</template>

<script>
import Button from './Button.vue'

export default {
  components: {
    Button,
  },

  props: {
    themes: {
      type: Array,
      required: true,
    },
  },

  methods: {
    getBackground(idx) {
      switch (idx) {
        case 0:
          return '#e2f1e8'
        case 2:
          return '#f1dada'
        case 4:
          return '#f1f1e2'

        default:
          return '#fff'
      }
    },
  },
}
</script>

<style scoped>
.container {
  height: 174px;
  padding: 0 40px;

  display: flex;
  align-items: center;
  justify-content: space-between;
}

.container--buttons {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.title {
  font-family: 'Anybody', serif;
  font-size: 51px;
  font-weight: 700;

  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
