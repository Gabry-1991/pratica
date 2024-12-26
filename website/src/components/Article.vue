<template>
  <div class="container--article" :class="{ 'container--article-text-black': mobileBgWhite }">
    <div
      v-if="detachedBackground"
      class="detached-background"
      :class="{ centered: detachedBackground === 'url(backgrounds/smile.jpeg)' }"
    >
      <Label v-if="detachedBackground === 'url(backgrounds/ghiacciai.png)'" padding="16px">
        <template #content>
          <i class="fa-solid fa-image icon-big" />
        </template>
      </Label>

      <Label
        v-if="detachedBackground === 'url(backgrounds/ghiacciai.png)'"
        padding="13px"
        no-shadow
      >
        <template #content>
          <i class="fa-solid fa-play icon" />
        </template>
      </Label>

      <div
        v-if="detachedBackground === 'url(backgrounds/smile.jpeg)'"
        class="container--detached-title"
      >
        <h3 class="detached-title">Intervista a Mariangela Cassano</h3>
      </div>
    </div>

    <div>
      <Label
        :background="labelBackground"
        :background-mobile="labelBackgroundMobile"
        padding="4px 8px"
        class="label"
      >
        <template #content>
          <span>{{ label }}</span>
        </template>
      </Label>
    </div>

    <div
      v-if="soundWave"
      class="container--soundwave"
      :class="{ 'container--soundwave-long': soundWaveLong }"
    >
      <i class="fa-solid fa-pause icon" />
      <img
        :src="soundWave"
        alt="sound wave"
        class="soundwave"
        :class="{ 'soundwave-long': soundWaveLong }"
      />
      <span>-03:34</span>
    </div>

    <h3 class="title">{{ title }}</h3>

    <div class="container--author" :class="{ 'author-vertical': authorVertical }">
      <div class="container--image">
        <img :src="authorImg" alt="author image" class="image" />
        <img
          :src="authorImgMobile ? authorImgMobile : authorImg"
          alt="author image"
          class="image-mobile"
        />
      </div>

      <div class="container--details" :class="{ 'details-vertical': authorVertical }">
        <div class="author-name">Di {{ authorName }}</div>
        <div class="author-name-mobile">
          Di {{ authorNameMobile ? authorNameMobile : authorName }}
        </div>
        <div class="date">{{ date }}</div>
      </div>
    </div>

    <div v-if="!hideArrow" class="container--button">
      <button class="button">
        <i class="fa-solid fa-arrow-right icon" />
      </button>
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
    label: {
      type: String,
      required: true,
    },
    labelBackground: {
      type: String,
      default: '#fff',
    },
    labelBackgroundMobile: {
      type: String,
      default: '#fff',
    },
    title: {
      type: String,
      required: true,
    },
    titleSize: {
      type: String,
      required: true,
    },
    titleSizeMobile: {
      type: String,
      default: '',
    },
    titleLineHeight: {
      type: String,
      default: '',
    },
    titleLineHeightMobile: {
      type: String,
      default: '',
    },
    titleWidthMobile: {
      type: String,
      default: '100%',
    },
    authorImg: {
      type: String,
      required: true,
    },
    authorImgMobile: {
      type: String,
      default: '',
    },
    authorName: {
      type: String,
      required: true,
    },
    authorNameMobile: {
      type: String,
      default: '',
    },
    date: {
      type: String,
      required: true,
    },
    authorVertical: {
      type: Boolean,
      default: false,
    },
    hideArrow: {
      type: Boolean,
      default: false,
    },
    soundWave: {
      type: String,
      default: '',
    },
    soundWaveLong: {
      type: Boolean,
      default: false,
    },
    detachedBackground: {
      type: String,
      default: '',
    },
    detachedBackgroundHeight: {
      type: String,
      default: '201px',
    },
    mobileBgWhite: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style scoped>
.container--article {
  height: 100%;
  color: #fff;
  font-family: 'Anybody', serif;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.container--author {
  height: 48px;

  display: flex;
  align-items: flex-start;
  gap: 1rem;
}

.container--image {
  height: 48px;
  width: 48px;

  border-radius: 100%;
  overflow: hidden;
}

.image {
  height: 48px;
  width: 48px;
}

.image-mobile {
  display: none;
}

.container--details {
  height: 100%;
  padding: 4px 0;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.container--soundwave {
  color: #000;
  background: #fff;
  padding: 12px 16px;
  border-radius: 8px;
  width: 100%;
  height: 64px;

  display: flex;
  align-items: center;
  justify-content: space-between;
}

.container--soundwave-long {
  width: 115%;
}

.soundwave {
  height: 40px;
  width: 273px;
}

.soundwave-long {
  height: 40px;
  width: 407px;
}

.label {
  color: #000;
  text-transform: uppercase;
}

.title {
  font-size: v-bind(titleSize);
  line-height: v-bind(titleLineHeight);

  margin-top: 0;
  margin-bottom: 0;
}

.author-name {
  font-size: 14px;
}

.author-name-mobile {
  display: none;
}

.date {
  font-size: 10px;
}

.author-vertical {
  height: 112px;
  flex-direction: column;
}

.details-vertical {
  height: 48px;
}

.button {
  color: #fff;
  background: transparent;
  border: none;

  cursor: pointer;
}

.icon {
  font-size: 20px;
}

.detached-background {
  height: v-bind(detachedBackgroundHeight);
  width: 100%;
  border: 1px solid #000;
  margin-bottom: 0.8rem;
  display: none;

  background-image: v-bind(detachedBackground);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

@media (max-width: 1350px) {
  .soundwave {
    width: 190px;
  }

  .soundwave-long {
    width: 300px;
  }
}

@media (max-width: 1150px) {
  .soundwave {
    width: 110px;
  }

  .soundwave-long {
    width: 180px;
  }
}

@media (max-width: 800px) {
  .title {
    font-size: v-bind(titleSizeMobile);
    line-height: v-bind(titleLineHeightMobile);
    width: v-bind(titleWidthMobile);
  }

  .container--article-text-black {
    color: #000;
  }

  .container--image {
    height: 32px;
    width: 32px;
  }

  .author-vertical {
    height: 40px;
    flex-direction: row;
  }

  .container--author {
    height: 40px;

    align-items: center;
  }

  .image {
    display: none;
  }

  .image-mobile {
    display: block;
    height: 32px;
    width: 32px;
  }

  .author-name {
    display: none;
  }

  .author-name-mobile {
    display: block;
    font-size: 14px;
  }

  .icon-big {
    font-size: 22px;
  }

  .icon {
    font-size: 18px;
  }

  .container--detached-title {
    width: 87.5%;
    margin-bottom: 1.25rem;
  }

  .detached-background {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    justify-content: flex-end;
    gap: 1rem;
  }

  .centered {
    align-items: center;
    justify-content: flex-end;
  }

  .detached-title {
    color: #fff;
    font-size: 24px;
    line-height: 32px;
    font-weight: 700;
    margin-top: 0;
    margin-bottom: 0;
  }

  .details-vertical {
    height: 100%;
  }

  .container--button {
    display: none;
  }

  .container--soundwave {
    border: 1px solid #ccc;
  }

  .soundwave {
    width: 231px;
  }

  .container--soundwave-long {
    width: 100%;
  }
}
</style>
