<template>
  <div class="container--main-articles">
    <div class="container--article-1">
      <div class="article article-1">
        <Article
          :label="article1.label"
          :title="article1.title"
          :title-size="article1.titleSize"
          :title-size-mobile="article1.titleSizeMobile || article1.titleSize"
          :title-line-height="article1.titleLineHeight"
          :title-line-height-mobile="article1.titleLineHeightMobile || article1.titleLineHeight"
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
          :label-background-mobile="article2.labelBackgroundMobile || article2.labelBackground"
          :title="article2.title"
          :title-size="article2.titleSize"
          :title-size-mobile="article2.titleSizeMobile || article2.titleSize"
          :title-line-height="article2.titleLineHeight"
          :title-line-height-mobile="article2.titleLineHeightMobile || article2.titleLineHeight"
          :author-img="article2.authorImg"
          :author-img-mobile="article2.authorImgMobile"
          :author-name="article2.authorName"
          :author-name-mobile="article2.authorNameMobile"
          :date="article2.date"
          author-vertical
          detached-background="url(backgrounds/ghiacciai.png)"
          detached-background-height="201px"
          mobile-bg-white
        />
      </div>
    </div>
    <div class="container--article-3">
      <div class="article article-3">
        <Article
          :label="article3.label"
          :label-background="article3.labelBackground"
          :label-background-mobile="article3.labelBackgroundMobile || article3.labelBackground"
          :title="article3.title"
          :title-size="article3.titleSize"
          :title-size-mobile="article3.titleSizeMobile || article3.titleSize"
          :title-line-height="article3.titleLineHeight"
          :title-line-height-mobile="article3.titleLineHeightMobile || article3.titleLineHeight"
          :title-width-mobile="article3.titleWidthMobile"
          :author-img="article3.authorImg"
          :author-name="article3.authorName"
          :date="article3.date"
          :sound-wave="article3.soundWave"
          author-vertical
          sound-wave-long
          mobile-bg-white
        />
      </div>
    </div>
    <div class="container--article-4">
      <div class="article article-4">
        <Article
          :label="article4.label"
          :label-background="article4.labelBackground"
          :label-background-mobile="article4.labelBackgroundMobile || article4.labelBackground"
          :title="article4.title"
          :title-size="article4.titleSize"
          :title-size-mobile="article4.titleSizeMobile || article4.titleSize"
          :title-line-height="article4.titleLineHeight"
          :title-line-height-mobile="article4.titleLineHeightMobile || article4.titleLineHeight"
          :title-width-mobile="article4.titleWidthMobile"
          :author-img="article4.authorImg"
          :author-name="article4.authorName"
          :date="article4.date"
          author-vertical
          mobile-bg-white
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
        titleSizeMobile: '24px',
        titleLineHeight: '54px',
        titleLineHeightMobile: '32px',
        authorImg: 'authors/author-1.jpeg',
        authorName: 'Alessandro Puglia',
        date: '29 Giugno 2022',
      },
      article2: {
        label: 'allarmi',
        labelBackground: 'var(--label-green)',
        title: 'Il collasso dei ghiacciai negli scatti del fotografo ambiantale Fabiano Ventura',
        titleSize: '32px',
        titleSizeMobile: '20px',
        titleLineHeight: '46px',
        titleLineHeightMobile: '30px',
        authorImg: 'authors/author-2.png',
        authorImgMobile: 'authors/author-14.jpeg',
        authorName: 'Ugo Lombi',
        authorNameMobile: 'Gilda Sciortino',
        date: '14 Luglio 2022',
      },
      article3: {
        label: 'esperimenti',
        labelBackground: 'var(--label-blue)',
        title: 'Gli startupper? Li trovi al bistrot. Così il Dumbo incuba relazioni',
        titleSize: '24px',
        titleSizeMobile: '14px',
        titleLineHeight: '32px',
        titleLineHeightMobile: '24px',
        titleWidthMobile: '80%',
        authorImg: 'authors/author-3.jpeg',
        authorName: 'Diletta Grella',
        date: '14 Luglio 2022',
        soundWave: 'soundwave.png',
      },
      article4: {
        label: 'ucraina',
        labelBackground: 'var(--label-blue)',
        labelBackgroundMobile: 'var(--label-red)',
        title: 'Nelle città italiane tutti in piazza per e con Kiev',
        titleSize: '24px',
        titleSizeMobile: '14px',
        titleLineHeight: '32px',
        titleLineHeightMobile: '24px',
        titleWidthMobile: '84%',
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
  grid-template-columns: 57% 43%;
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
  height: 60%;
  width: 57%;
  padding: 44px 40px;
}

.article-2 {
  height: 47.5%;
  width: 92%;
  padding: 44px 40px;
}

.article-3 {
  height: 100%;
  width: 90%;
}

.article-4 {
  height: 100%;
  width: 90%;
}

@media (max-width: 1245px) {
  .article-1 {
    height: 70%;
  }

  .container--article-3 {
    background-size: cover;
  }
}

@media (max-width: 800px) {
  .container--main-articles {
    height: fit-content;
    grid-template-columns: 100%;
    grid-template-rows: 320px 456px 268px 188px;
  }

  .container--article-1 {
    background-size: 145%;
    background-position: 50% 50%;
  }

  .container--article-2 {
    background: #fff;
    border-bottom: 1px solid #000;

    grid-row: 2;

    display: flex;
    align-items: flex-end;
  }

  .container--article-3 {
    background: #fff;
    border-bottom: 1px solid #000;
  }

  .container--article-4 {
    background: #fff;
    border-bottom: 1px solid #000;
  }

  .article-1 {
    height: 75%;
    width: 85%;

    padding: 24px 16px;
  }

  .article-2 {
    height: 100%;
    width: 100%;
    padding: 24px 16px;
  }

  .article-3 {
    width: 100%;
    padding: 24px 16px;
  }

  .article-4 {
    width: 100%;
    padding: 24px 16px;
  }
}
</style>
