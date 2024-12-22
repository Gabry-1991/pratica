<template>
  <div class="container">
    <div class="container--article-1"></div>
    <div class="container--article-2"></div>
    <div class="container--article-3"></div>
    <div class="container--article-4"></div>
  </div>
</template>

<style scoped>
.container {
  height: calc(506px + 845px);
  filter: brightness(0.7);

  display: grid;
  grid-template-columns: 0.565fr 0.435fr;
  grid-template-rows: 506px 471px 374px;
}

.container--article-1 {
  background-image: url('backgrounds/soccorso.jpeg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 10% 50%;

  grid-column: 1 / -1;
}

.container--article-2 {
  background-image: url('backgrounds/ghiacciai.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 50% 50%;

  grid-row: 2 / -1;
}

.container--article-3 {
  background-image: url('backgrounds/locale.jpeg');
  background-size: 165%;
  background-repeat: no-repeat;
  background-position: 67.5% 50%;
}

.container--article-4 {
  background-image: url('backgrounds/bandiera.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 50% 50%;
}
</style>
