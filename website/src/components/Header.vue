<template>
  <div class="container--general">
    <div class="container--breadcrumbs">
      <div class="breadcrumbs">
        <span>Contribuisci</span>
        <span>Abbonati</span>
      </div>

      <div class="accedi">
        <i class="fa-regular fa-user" />
        <span>Accedi</span>
      </div>
    </div>

    <Divider />

    <div class="container--menu">
      <div class="menu--button">
        <div class="menu--icon">
          <i class="fa-solid fa-bars" />
        </div>
      </div>

      <div class="menu--button">
        <div class="menu--icon">
          <i class="fa-solid fa-magnifying-glass" />
        </div>
      </div>
    </div>

    <Divider />

    <div class="d-flex align-items-center justify-content-between">
      <div class="container--tabs">
        <div v-for="(tab, idx) of themes" :key="idx" class="tab">
          {{ tab }}
        </div>
      </div>

      <div class="container--toggle">
        <span class="letters">Aa</span>

        <Label padding="6px">
          <template #content>
            <i class="fa-solid fa-mountain icon" />
          </template>
        </Label>
      </div>
    </div>
  </div>

  <Divider />
</template>

<script>
import Divider from './Divider.vue'
import Label from './Label.vue'

export default {
  components: {
    Divider,
    Label,
  },

  props: {
    themes: {
      type: Array,
      required: true,
    },
  },
}
</script>

<style scoped lang="scss">
.container--general {
  width: 100%;
  background: #fff;
}
.container--breadcrumbs {
  font-family: 'Anybody', serif;
  height: 48px;
  font-size: 14px;
  padding: 0 40px;

  display: flex;
  align-items: center;
  justify-content: space-between;
}

.container--menu {
  height: 96px;
  width: 100%;

  display: flex;
  align-items: center;
  justify-content: space-between;
}

.breadcrumbs {
  display: flex;
  gap: 1.5rem;
}

.accedi {
  display: flex;
  align-items: center;
  gap: 0.7rem;
}

.menu {
  height: 50%;
}

.menu--button {
  width: 96px;
  height: 100%;

  display: flex;
  align-items: center;
  justify-content: center;

  &:first-of-type {
    border-right: 1px solid #000;
  }
  &:last-of-type {
    border-left: 1px solid #000;
  }
}

.menu--icon {
  font-size: 19px;
  color: var(--primary-red);
}

.icon {
  font-size: 19px;
}

.container--tabs {
  font-family: 'Raleway', serif;
  font-size: 24px;
  font-weight: 700;

  height: 96px;
  padding: 0 40px;
  cursor: pointer;

  display: flex;
  align-items: center;
  gap: 1.8rem;
}

.tab {
  height: 100%;
  border-radius: 2px;

  display: flex;
  align-items: center;
  justify-content: center;

  &:first-of-type {
    box-shadow: 0 -9px 0 var(--primary-red) inset;
  }
}

.container--toggle {
  padding: 0 40px;

  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.letters {
  font-size: 20px;
}
</style>
