<template>
  <div class="container--dropdown" :class="{ 'container--dropdown--visible': dropdownVisible }">
    <div v-for="section of menuSections" class="menu-section">
      <div class="container--text">
        <h3 class="title">{{ section.title }}</h3>
        <span class="sub">{{ section.sub }}</span>
      </div>
    </div>

    <div v-for="service of menuServices" class="menu-service">
      <span class="sub">{{ service }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    dropdownVisible: {
      type: Boolean,
      default: false,
    },
  },

  data() {
    return {
      menuSections: [
        {
          title: 'Articoli',
          sub: 'Trend, dati e novità del Terzo Settore.',
        },
        {
          title: 'Storie',
          sub: 'Letture ed approfondimenti dei fenomeni complessi.',
        },
        {
          title: 'Interviste',
          sub: 'Racconti reali di persone ed organizzazioni.',
        },
        {
          title: 'Opinioni',
          sub: 'Riflessioni e confronti dei nostri opinionisti.',
        },
        {
          title: 'Podcast',
          sub: 'Un luogo per dare voce ai protagonisti della sostenibilità.',
        },
        {
          title: 'Bookazine',
          sub: 'Una rivista da leggere e un libro da conservare.',
        },
      ],

      menuServices: [
        'Chi siamo',
        'Comitato editoriale',
        'Servizi',
        ' Agenda/Eventi',
        "Mappa dell'attivismo",
        'Inchieste crowdfunding',
      ],
    }
  },
}
</script>

<style scoped>
.container--dropdown {
  opacity: 0;
  pointer-events: none;
  visibility: none;

  height: auto;
  width: 100.05%;
  background: #000;
  padding-top: 1px;
  font-family: 'Anybody', serif;
  z-index: 999999999999;

  position: absolute;
  top: 0%;
  left: 0;

  display: grid;
  grid-template-columns: repeat(6, 1fr);
  grid-template-rows: 313px 313px 130px;
  gap: 1px;

  transition: all 0.2s ease-out;
}

.container--dropdown--visible {
  opacity: 1;
  pointer-events: all;
  visibility: visible;

  top: 100%;
}

.menu-section {
  height: 100%;
  background: #fff;

  grid-column: span 2;

  display: flex;
  align-items: flex-end;
  justify-content: flex-start;
}

.menu-service {
  height: 100%;
  background: #fff;

  display: flex;
  align-items: center;
  justify-content: center;
}

.container--text {
  height: 166px;
  padding: 40px;

  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.title {
  font-size: 48px;
  line-height: 48px;
  margin-top: 0;
  margin-bottom: 0;
}

.sub {
  font-size: 14px;
  line-height: 24px;
}
</style>
