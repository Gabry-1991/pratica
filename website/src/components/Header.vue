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

    <div class="container--menu">
      <div class="menu">
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
      <div class="tabs">
        <div v-for="(tab, idx) of tabs" :key="idx" class="tab">
          {{ tab }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tabs: [
        'Tutti i temi',
        'Ambiente',
        'Economia',
        'Mondo',
        'Non profit',
        'Politica',
        'Società',
        'Welfare',
      ],
    }
  },
}
</script>

<style scoped lang="scss">
.container--general {
  padding: 0 40px;
  border: 1px solid red;
}
.container--breadcrumbs {
  height: 48px;
  font-size: 14px;

  display: flex;
  align-items: center;
  justify-content: space-between;
}

.container--menu {
  height: 192px;
  border-top: 1px solid #000;
  border-bottom: 1px solid #000;
}

.breadcrumbs {
  display: flex;
  gap: 1.5rem;
}

.accedi {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.menu {
  height: 50%;
  border-bottom: 1px solid #000;

  display: flex;
  justify-content: space-between;
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

.tabs {
  height: 50%;

  display: flex;
  align-items: center;
  gap: 1rem;
}

.tab {
}
</style>
