<template>
  <div class="container--general">
    <div class="container--empty"></div>

    <div class="container--breadcrumbs">
      <div class="breadcrumbs">
        <button>
          <span class="breadcrumb">Contribuisci</span>
        </button>

        <Divider vertical class="breadcrumb-divider" />

        <button>
          <span class="breadcrumb">Abbonati</span>
        </button>
      </div>

      <button>
        <div class="accedi">
          <i class="fa-regular fa-user" />
          <span>Accedi</span>
        </div>
      </button>
    </div>

    <Divider />

    <div class="container--menu">
      <div class="menu--button">
        <div class="menu--icon">
          <i class="fa-solid fa-bars" />
        </div>
      </div>

      <div class="menu--button">
        <div>
          <button class="menu--icon">
            <i class="fa-solid fa-magnifying-glass" />
          </button>
        </div>
      </div>

      <!-- <Menu /> -->
    </div>

    <Divider />

    <div class="container--all-themes">
      <div class="container--tabs">
        <div v-for="(tab, idx) of themes" :key="idx" class="tab">
          {{ tab }}
        </div>
      </div>

      <div class="container--toggle">
        <span class="letters">Aa</span>

        <Label padding="6px">
          <template #content>
            <i class="fa-solid fa-image icon" />
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
import Menu from './Menu.vue'

export default {
  components: {
    Divider,
    Label,
    Menu,
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
  position: relative;

  display: flex;
  align-items: center;
  justify-content: space-between;
}

.container--all-themes {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.container--empty {
  display: none;
  height: 44px;
  border-bottom: 1px solid #000;
}

.breadcrumbs {
  height: 100%;

  display: flex;
  align-items: center;
  gap: 1.5rem;
}

.breadcrumb {
  font-size: 14px;
}

.breadcrumb-divider {
  display: none;
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
  position: relative;

  display: flex;
  align-items: center;
  justify-content: center;

  &:first-of-type::after {
    content: '';
    height: 9px;
    width: 100%;
    border-radius: 2px;
    background: var(--primary-red);

    position: absolute;
    left: 0;
    bottom: 0;
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

@media (max-width: 1150px) {
  .container--toggle {
    display: none;
  }
}

@media (max-width: 1030px) {
  .container--tabs {
    display: none;
  }

  .container--empty {
    display: block;
  }

  .container--menu {
    height: 52px;
  }

  .breadcrumbs {
    width: 100%;
    justify-content: space-around;
  }

  .breadcrumb-divider {
    display: block;
  }

  .menu--button {
    width: 52px;
  }

  .accedi {
    display: none;
  }
}
</style>
