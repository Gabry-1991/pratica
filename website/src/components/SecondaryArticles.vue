<template>
  <div class="container--secondary-articles">
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
          author-vertical
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
          :title-line-height-mobile="article2.titleLineHeightMobile || article2.titleLineHeight"
          :title-line-height="article2.titleLineHeight"
          :author-img="article2.authorImg"
          :author-name="article2.authorName"
          :date="article2.date"
          author-vertical
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
          :author-img="article3.authorImg"
          :author-name="article3.authorName"
          :date="article3.date"
          :sound-wave="article3.soundWave"
          author-vertical
          mobile-bg-white
        />
      </div>
    </div>
    <div class="container--second-row">
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
            :author-img="article4.authorImg"
            :author-name="article4.authorName"
            :date="article4.date"
            :sound-wave="article4.soundWave"
            author-vertical
            mobile-bg-white
          />
        </div>
      </div>

      <Divider vertical class="divider" />

      <div class="container--article-5">
        <div class="article article-5">
          <Article
            :label="article5.label"
            :label-background="article5.labelBackground"
            :label-background-mobile="article5.labelBackgroundMobile || article5.labelBackground"
            :title="article5.title"
            :title-size="article5.titleSize"
            :title-size-mobile="article5.titleSizeMobile || article5.titleSize"
            :title-line-height="article5.titleLineHeight"
            :title-line-height-mobile="article5.titleLineHeightMobile || article5.titleLineHeight"
            :author-img="article5.authorImg"
            :author-name="article5.authorName"
            :date="article5.date"
            detached-background="url(backgrounds/smile.jpeg)"
            detached-background-height="358px"
            mobile-bg-white
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Article from './Article.vue'
import Divider from './Divider.vue'

export default {
  components: {
    Article,
    Divider,
  },

  data() {
    return {
      article1: {
        label: 'progetto arca',
        title: '“Qui Odessa”, fotografie, progetti e solidarietà',
        titleSize: '24px',
        titleSizeMobile: '14px',
        titleLineHeight: '32px',
        titleLineHeightMobile: '24px',
        authorImg: 'authors/author-5.png',
        authorName: 'Di Redazione',
        date: '13 Luglio 2022',
      },
      article2: {
        label: 'adolescenti',
        labelBackground: 'var(--label-green)',
        labelBackgroundMobile: 'var(--label-green)',
        title: 'Storie fra ragazzi permeate di violenza. A Napoli 12enne sfregiata da 17enne',
        titleSize: '24px',
        titleSizeMobile: '14px',
        titleLineHeight: '32px',
        titleLineHeightMobile: '24px',
        authorImg: 'authors/author-6.jpeg',
        authorName: 'Luca Cereda',
        date: '13 Luglio 2022',
      },
      article3: {
        label: 'economia civile',
        labelBackground: 'var(--label-purple)',
        labelBackgroundMobile: 'var(--label-purple)',
        title: '“Co-agitiamo”, Tiggiano una cooperativa di comunità contro lo spopolamento',
        titleSize: '24px',
        titleSizeMobile: '14px',
        titleLineHeight: '32px',
        titleLineHeightMobile: '24px',
        authorImg: 'authors/author-7.jpeg',
        authorName: 'Emiliano Moccia',
        date: '12 Luglio 2022',
      },
      article4: {
        label: 'sport',
        labelBackground: 'var(--label-purple)',
        labelBackgroundMobile: 'var(--label-purple)',
        title: 'Troppi abusi nello sport minorile, il governo interviene',
        titleSize: '24px',
        titleSizeMobile: '14px',
        titleLineHeight: '32px',
        titleLineHeightMobile: '24px',
        authorImg: 'authors/author-8.jpeg',
        authorName: 'Diletta Grella',
        date: '7 Luglio 2022',
        soundWave: 'soundwave-short.png',
      },
      article5: {
        label: 'società',
        labelBackground: 'var(--label-green)',
        labelBackgroundMobile: 'var(--label-green)',
        title: 'Donne e nuove generazioni: con loro riparte l’Italia',
        titleSize: '40px',
        titleSizeMobile: '20px',
        titleLineHeight: '48px',
        titleLineHeightMobile: '30px',
        authorImg: 'authors/author-4.jpeg',
        authorName: 'Anna Spena',
        date: '7 Luglio 2022',
      },
    }
  },
}
</script>

<style scoped>
.container--secondary-articles {
  height: calc(436px + 482px);

  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 436px 482px;
  gap: 1px;
}

.container--article-1 {
  background: var(--primary-red);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 10% 50%;
}

.container--article-2 {
  background-image: url('backgrounds/ragazza.jpeg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 50% 50%;
}

.container--article-3 {
  background-image: url('backgrounds/riunione.jpeg');
  background-size: 165%;
  background-repeat: no-repeat;
  background-position: 67.5% 50%;
}

.container--article-4 {
  width: 33.3%;

  background-image: url('backgrounds/boxe.jpeg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 50% 50%;
}

.container--article-5 {
  width: 66.6%;
  background-image: url('backgrounds/smile.jpeg');
  background-size: 125%;
  background-repeat: no-repeat;
  background-position: 100% 40%;

  display: flex;
  align-items: flex-start;
  justify-content: flex-end;
}

.container--second-row {
  grid-column: 1 / -1;

  display: flex;
}

.article {
  padding: 40px;
}

.article-1 {
  height: 100%;
  width: 90%;
}

.article-2 {
  height: 100%;
  width: 100%;
}

.article-3 {
  height: 100%;
  width: 90%;
}

.article-4 {
  height: 100%;
  width: 100%;
}

.article-5 {
  height: 77.5%;
  width: 54%;
}

@media (max-width: 800px) {
  .container--secondary-articles {
    height: fit-content;
    grid-template-columns: 100%;
    grid-template-rows: 164px 188px 188px calc(268px + 614px);
  }

  .container--article-1 {
    border-top: 1px solid #000;
    border-bottom: 1px solid #000;
  }

  .container--article-2 {
    background: #fff;
    border-bottom: 1px solid #000;
  }

  .container--article-3 {
    background: #fff;
    border-bottom: 1px solid #000;
  }

  .container--article-4 {
    height: 268px;
    width: 100%;
    background: #fff;
    border-bottom: 1px solid #000;
  }

  .container--article-5 {
    height: 614px;
    width: 100%;
    background: #fff;
    border-bottom: 1px solid #000;
  }

  .container--second-row {
    flex-direction: column;
  }

  .divider {
    display: none;
  }

  .article-1 {
    height: 100%;
    width: 100%;

    padding: 24px 16px;
  }

  .article-2 {
    height: 100%;
    width: 100%;
    padding: 24px 16px;
  }

  .article-3 {
    height: 100%;
    width: 100%;
    padding: 24px 16px;
  }

  .article-4 {
    width: 100%;
    padding: 24px 16px;
  }

  .article-5 {
    height: 100%;
    width: 100%;
    padding: 40px 16px;
  }
}
</style>
