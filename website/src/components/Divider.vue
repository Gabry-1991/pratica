<template>
  <div
    class="divider"
    :class="{ 'divider--horizontal': !vertical, 'divider--vertical': vertical }"
  ></div>
</template>

<script>
export default {
  props: {
    vertical: { type: Boolean, default: false },
  },
}
</script>

<style scoped>
.divider {
  background: #000;
}
.divider--horizontal {
  height: 1px;
  width: 100%;
}
.divider--vertical {
  height: 100%;
  width: 1px;
}
</style>
