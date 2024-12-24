<template>
  <Layout />
</template>

<script>
import Layout from './components/Layout.vue'

export default {
  components: {
    Layout,
  },
}
</script>

<style>
button {
  border: none;
  background: transparent;
  cursor: pointer;
  transform: scale(1);

  transition: all 0.2s ease-out;
}

button:hover {
  transform: scale(1.05);
}

.d-flex {
  display: flex;
}

.d-none {
  display: none !important;
}

.align-items-center {
  align-items: center;
}

.justify-content-center {
  justify-content: center;
}

.justify-content-between {
  justify-content: space-between;
}

.flex {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
