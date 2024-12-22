<template>
  <Header :themes="themes" />

  <DividerSection title="Tutti i temi">
    <template #content>
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
    </template>
  </DividerSection>

  <MainArticles />

  <DividerSection background="#f4f1de" title="Il tuo supporto è fondamentale" title-size="40px">
    <template #content>
      <div class="flex">
        <span :style="{ 'font-size': '14px' }">Dai il tuo contributo</span>&nbsp;
        <i class="fa-solid fa-arrow-right icon" />
      </div>
    </template>
  </DividerSection>

  <SecondaryArticles />

  <Bookmark />

  <Blog />
</template>

<script>
import Header from './Header.vue'
import DividerSection from './DividerSection.vue'
import MainArticles from './MainArticles.vue'
import SecondaryArticles from './SecondaryArticles.vue'
import Bookmark from './Bookmark.vue'
import Label from './Label.vue'
import Blog from './Blog.vue'

export default {
  components: {
    Header,
    DividerSection,
    MainArticles,
    SecondaryArticles,
    Bookmark,
    Label,
    Blog,
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
.icon {
  font-size: 16px;
}

@media (max-width: 1030px) {
  .tab {
    background: #fff;
  }

  .icon {
    font-size: 19px;
  }
}
</style>
