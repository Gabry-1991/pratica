<template>
  <div class="container--divider">
    <div class="container--title">
      <h2 class="title" :class="{ 'title-md': title === 'Il tuo supporto è fondamentale' }">
        {{ title }}
      </h2>
      <i
        class="fa-solid fa-chevron-down icon"
        :class="{ 'd-none': title === 'Il tuo supporto è fondamentale' }"
      />
    </div>

    <div class="container--content">
      <slot name="content"> </slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    background: {
      type: String,
      default: 'transparent',
    },
    title: {
      type: String,
      required: true,
    },
    titleSize: {
      type: String,
      default: '51px',
    },
  },
}
</script>

<style scoped>
.container--divider {
  font-family: 'Anybody', serif;
  font-weight: 700;
  height: 174px;
  padding: 0 40px;
  background: v-bind(background);

  display: flex;
  align-items: center;
  justify-content: space-between;
}

.container--content {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.container--title {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
}

.title {
  font-size: v-bind(titleSize);

  display: flex;
  align-items: center;
  justify-content: space-between;
}

.icon {
  display: none;
}

@media (max-width: 1030px) {
  .container--divider {
    padding: 0 16px;

    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
  }

  .container--content {
    padding-bottom: 24px;

    flex-wrap: wrap;
    gap: 0.75rem 0.5rem;
  }

  .title {
    font-size: 28px;
  }

  .title-md {
    font-size: 24px;
    line-height: 32px;
  }

  .icon {
    display: block;
    font-size: 19px;
  }
}
</style>
