<template>
  <div class="label">
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
    padding: {
      type: String,
      default: '12px 16px',
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
</style>
