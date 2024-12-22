<template>
  <div class="container--article">
    <div>
      <Label :background="labelBackground" padding="4px 8px" class="label">
        <template #content>
          <span>{{ label }}</span>
        </template>
      </Label>
    </div>

    <div v-if="soundWave" class="container--soundwave">
      <i class="fa-solid fa-pause icon" />
      <img :src="soundWave" alt="sound wave" />
      <span>-03:34</span>
    </div>

    <h3 class="title">{{ title }}</h3>

    <div class="container--author" :class="{ 'author-vertical': authorVertical }">
      <div class="container--image">
        <img height="48" width="48" :src="authorImg" alt="author image" />
      </div>

      <div class="container--details" :class="{ 'details-vertical': authorVertical }">
        <div class="author-name">Di {{ authorName }}</div>
        <div class="date">{{ date }}</div>
      </div>
    </div>

    <div v-if="!hideArrow">
      <i class="fa-solid fa-arrow-right" />
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
    title: {
      type: String,
      required: true,
    },
    titleSize: {
      type: String,
      required: true,
    },
    titleLineHeight: {
      type: String,
      required: true,
    },
    authorImg: {
      type: String,
      required: true,
    },
    authorName: {
      type: String,
      required: true,
    },
    date: {
      type: String,
      required: true,
    },
    authorVertical: {
      type: Boolean,
      required: true,
    },
    hideArrow: {
      type: Boolean,
      default: false,
    },
    soundWave: {
      type: String,
      default: '',
    },
  },
}
</script>

<style scoped>
.container--article {
  color: #fff;
  font-family: 'Anybody', serif;

  display: flex;
  flex-direction: column;
  gap: 1.5rem;
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
  width: 115%;

  display: flex;
  align-items: center;
  justify-content: space-between;
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

.icon {
  /* font-size: 19px; */
}
</style>
