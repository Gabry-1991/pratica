<template>
  <div class="container--article" :class="{ 'container--article-text-black': mobileBgWhite }">
    <div v-if="detachedBackground" class="detached-background">
      <Label padding="16px">
        <template #content>
          <i class="fa-solid fa-image icon-big" />
        </template>
      </Label>

      <Label padding="13px" no-shadow>
        <template #content>
          <i class="fa-solid fa-play icon" />
        </template>
      </Label>
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

    <div v-if="soundWave" class="container--soundwave" :class="{ 'soundwave-long': soundWaveLong }">
      <i class="fa-solid fa-pause icon" />
      <img :src="soundWave" alt="sound wave" class="soundwave" />
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
      required: true,
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
      type: Boolean,
      default: false,
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

.soundwave-long {
  width: 115%;
}

.soundwave {
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
  height: 201px;
  width: 100%;
  border: 1px solid #000;
  margin-bottom: 0.8rem;
  display: none;

  background-image: url('backgrounds/ghiacciai.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

@media (max-width: 1350px) {
  .soundwave {
    width: 300px;
  }
}

@media (max-width: 1150px) {
  .soundwave {
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

  .detached-background {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    justify-content: flex-end;
    gap: 1rem;
  }

  .author-vertical {
    height: 48px;
    flex-direction: row;
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

  .soundwave-long {
    width: 100%;
  }
}
</style>
