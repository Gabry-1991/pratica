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
.d-flex {
  display: flex;
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
