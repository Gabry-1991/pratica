<template>
  <div class="container--main-articles">
    <div class="container--article-1">
      <div class="article article-1">
        <Article
          :label="article1.label"
          :title="article1.title"
          :title-size="article1.titleSize"
          :title-line-height="article1.titleLineHeight"
          :author-img="article1.authorImg"
          :author-name="article1.authorName"
          :date="article1.date"
          hide-arrow
        />
      </div>
    </div>
    <div class="container--article-2">
      <div class="article article-2">
        <Article
          :label="article2.label"
          :label-background="article2.labelBackground"
          :title="article2.title"
          :title-size="article2.titleSize"
          :title-line-height="article2.titleLineHeight"
          :author-img="article2.authorImg"
          :author-name="article2.authorName"
          :date="article2.date"
          author-vertical
        />
      </div>
    </div>
    <div class="container--article-3">
      <div class="article article-3">
        <Article
          :label="article3.label"
          :label-background="article3.labelBackground"
          :title="article3.title"
          :title-size="article3.titleSize"
          :title-line-height="article3.titleLineHeight"
          :author-img="article3.authorImg"
          :author-name="article3.authorName"
          :date="article3.date"
          :sound-wave="article3.soundWave"
          author-vertical
        />
      </div>
    </div>
    <div class="container--article-4">
      <div class="article article-4">
        <Article
          :label="article4.label"
          :label-background="article4.labelBackground"
          :title="article4.title"
          :title-size="article4.titleSize"
          :title-line-height="article4.titleLineHeight"
          :author-img="article4.authorImg"
          :author-name="article4.authorName"
          :date="article4.date"
          author-vertical
        />
      </div>
    </div>
  </div>
</template>

<script>
import Article from './Article.vue'

export default {
  components: {
    Article,
  },

  data() {
    return {
      article1: {
        label: 'migranti',
        title: "Roccella Jonica, la Lampedusa che l'Italia ignora",
        titleSize: '40px',
        titleLineHeight: '54px',
        authorImg: 'authors/author-1.jpeg',
        authorName: 'Alessandro Puglia',
        date: '29 Giugno 2022',
      },
      article2: {
        label: 'allarmi',
        labelBackground: 'var(--label-green)',
        title: 'Il collasso dei ghiacciai negli scatti del fotografo ambiantale Fabiano Ventura',
        titleSize: '32px',
        titleLineHeight: '46px',
        authorImg: 'authors/author-2.png',
        authorName: 'Ugo Lombi',
        date: '14 Luglio 2022',
      },
      article3: {
        label: 'esperimenti',
        labelBackground: 'var(--label-blue)',
        title: 'Gli startupper? Li trovi al bistrot. Così il Dumbo incuba relazioni',
        titleSize: '24px',
        titleLineHeight: '32px',
        authorImg: 'authors/author-3.jpeg',
        authorName: 'Diletta Grella',
        date: '14 Luglio 2022',
        soundWave: 'soundwave.png',
      },
      article4: {
        label: 'ucraina',
        labelBackground: 'var(--label-blue)',
        title: 'Nelle città italiane tutti in piazza per e con Kiev',
        titleSize: '24px',
        titleLineHeight: '32px',
        authorImg: 'authors/author-4.jpeg',
        authorName: 'Anna Spena',
        date: '14 Luglio 2022',
      },
    }
  },
}
</script>

<style scoped>
.container--main-articles {
  height: calc(506px + 845px);

  display: grid;
  grid-template-columns: 57% auto;
  grid-template-rows: 506px 471px 374px;
  gap: 1px;
}

.container--article-1 {
  background-image: url('backgrounds/soccorso.jpeg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 10% 50%;

  grid-column: 1 / -1;

  display: flex;
  align-items: flex-end;
}

.container--article-2 {
  background-image: url('backgrounds/ghiacciai.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 50% 50%;

  grid-row: 2 / -1;

  display: flex;
  align-items: flex-end;
}

.container--article-3 {
  background-image: url('backgrounds/locale.jpeg');
  background-size: 165%;
  background-repeat: no-repeat;
  background-position: 67.5% 50%;
}

.container--article-4 {
  background-image: url('backgrounds/bandiera.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 50% 50%;
}

.article {
  padding: 40px;
}

.article-1 {
  width: 57%;
}

.article-2 {
  width: 92%;
}

.article-3 {
  width: 90%;
}

.article-4 {
  width: 90%;
}
</style>
