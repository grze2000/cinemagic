<template>
  <section class="section movie-pass">
    <div class="movie-pass__info">
      <div class="section__subtitle">Promocje</div>
      <h2 class="section__title"><strong>Płać mniej</strong> ze zniżkami grupowymi i karnetami</h2>
      <router-link to="/movie-pass" class="movie-pass__button">
        <button class="btn--filled">Sprawdź</button>
      </router-link>
    </div>
    <div class="movie-pass__image-wrapper">
      <img src="https://fwcdn.pl/fpo/66/50/836650/7926222.3.jpg" alt="" class="movie-pass__image">
    </div>
    <div class="movie-pass__image-wrapper">
      <img src="https://fwcdn.pl/fpo/66/50/836650/7926222.3.jpg" alt="" class="movie-pass__image">
    </div>
    <div class="movie-pass__image-wrapper">
      <img src="https://fwcdn.pl/fpo/66/50/836650/7926222.3.jpg" alt="" class="movie-pass__image">
    </div>
    <div class="movie-pass__image-wrapper">
      <img src="https://fwcdn.pl/fpo/66/50/836650/7926222.3.jpg" alt="" class="movie-pass__image">
    </div>
  </section>
</template>

<script>
export default {
  name: 'MoviePass',
  setup() {
    
  },
}
</script>

<style lang="scss">
.movie-pass {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(8, 1fr);
  grid-gap: 30px;
  

  &__info {
    grid-column: 1 / 2;
    grid-row: 1 / 4;
  }

  &__image {
    width: 100%;
  }

  &__button {
    display: inline-block;
    margin-top: 15px;
  }

  .section__title {
    line-height: 1.1em;
    font-size: calc(3vw);
  }
  
  &__image-wrapper:nth-child(2) {
      grid-column: 1 / 2;
      grid-row: 4 / 9;
  }

  &__image-wrapper:nth-child(3) {
      grid-column: 2 / 3;
      grid-row: 1 / 5;
      text-align: center;
  }

  &__image-wrapper:nth-child(4) {
      grid-column: 2 / 3;
      grid-row: 5 / 9;
      text-align: center;
  }

  &__image-wrapper:nth-child(5) {
      grid-column: 3 / 4;
      grid-row: 2 / 7;
  }

  &__image-wrapper:nth-child(3) .movie-pass__image,
  &__image-wrapper:nth-child(4) .movie-pass__image {
    width: 80%;
  }
}
</style>