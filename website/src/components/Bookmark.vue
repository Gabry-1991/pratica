<template>
  <div class="container--bookmark">
    <div class="container--symbol">
      <img height="40" width="50" src="/symbol.png" alt="apici" class="symbol" />
      <img height="27" width="34" src="/symbol-mobile.png" alt="apici" class="symbol-mobile" />
    </div>

    <div class="container--text">
      <h2 class="title">Essere troppo seri non è cosa molto seria</h2>
      <span class="sub">[ Detto Africano ]</span>
    </div>
  </div>
</template>

<style scoped>
.container--bookmark {
  color: #fff;
  font-family: 'Anybody', serif;

  height: 246px;
  padding: 0 40px;
  border-top: 2px solid #fff;

  display: flex;
  align-items: center;
  gap: 0.6rem;

  background-image: url('backgrounds/bookmark.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 100% 67.5%;
}

.container--symbol {
  width: 100px;
  transform: translateY(-125%);

  display: flex;
  justify-content: center;
}

.symbol {
  display: block;
}

.symbol-mobile {
  display: none;
}

.container--text {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.title {
  font-size: 40px;
  font-weight: 700;
  margin-top: 0;
  margin-bottom: 0;
}

.sub {
  font-size: 16px;
  font-weight: 600;
  font-style: italic;
}

@media (max-width: 1030px) {
  .container--bookmark {
    height: 154px;
    color: #000;
    background: transparent;
    padding: 0 16px;
  }

  .container--symbol {
    width: 70px;
    transform: translateY(-170%);

    display: flex;
    justify-content: center;
  }

  .symbol {
    display: none;
  }

  .symbol-mobile {
    display: block;
  }

  .title {
    font-size: 24px;
    line-height: 32px;
  }
}
</style>
