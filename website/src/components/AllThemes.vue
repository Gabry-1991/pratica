<template>
  <div class="container">
    <h2 class="title">Tutti i temi</h2>

    <div class="container--buttons">
      <Label
        v-for="(tab, idx) of themes.slice(1)"
        :key="idx"
        :background="getBackground(idx)"
        class="tab"
      >
        <template #content>
          <span>{{ tab }}</span>
        </template>
      </Label>
    </div>
  </div>
</template>

<script>
import Label from './Label.vue'

export default {
  components: {
    Label,
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
          return 'var(--label-green)'
        case 2:
          return 'var(--label-red)'
        case 4:
          return 'var(--label-sand)'

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
