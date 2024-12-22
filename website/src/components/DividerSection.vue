<template>
  <div class="container--divider">
    <h2 class="title">{{ title }}</h2>

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

.title {
  font-size: v-bind(titleSize);

  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
