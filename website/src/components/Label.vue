<template>
  <div class="label" :class="{ 'no-shadow': noShadow, 'default-padding': padding === '12px 16px' }">
    <slot name="content"></slot>
  </div>
</template>

<script>
export default {
  props: {
    background: {
      type: String,
      default: '#fff',
    },
    backgroundMobile: {
      type: String,
      default: '#fff',
    },
    padding: {
      type: String,
      default: '12px 16px',
    },
    noShadow: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style scoped>
.label {
  font-family: 'Raleway', serif;
  font-size: 10px;
  font-weight: 700;
  text-transform: uppercase;

  background: v-bind(background);
  padding: v-bind(padding);
  width: fit-content;

  border: 1px solid #000;
  border-radius: 4px;
  box-shadow: -2px 2px 0 0 #000;
}

.no-shadow {
  box-shadow: none;
}

@media (max-width: 800px) {
  .label {
    background: v-bind(backgroundMobile);
  }
  .default-padding {
    padding: 12px 13px;
  }
}
</style>
