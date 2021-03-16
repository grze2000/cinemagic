<template>
  <section class="section now-showing">
    <div class="section__subtitle">Filmy</div>
    <h2 class="section__title"><strong>Aktualnie</strong> wyświetlane</h2>
    <div class="now-showing__list">
      <div class="now-showing__list-item movie">
        <img src="https://fwcdn.pl/fpo/66/50/836650/7926222.3.jpg" alt="" class="movie__image">
        <div class="movie__title">Czarna wdowa</div>
        <div class="movie__info">138 min</div>
        <div class="movie__info">Od 6 maja</div>
        <router-link to="/get-ticket">
          <button class="btn--small">Kup bilet</button>
        </router-link>
      </div>
      <div class="now-showing__list-item movie">
        <img src="https://fwcdn.pl/fpo/66/50/836650/7926222.3.jpg" alt="" class="movie__image">
        <div class="movie__title">Czarna wdowa</div>
        <div class="movie__info">138 min</div>
        <div class="movie__info">Od 6 maja</div>
        <router-link to="/get-ticket">
          <button class="btn--small">Kup bilet</button>
        </router-link>
      </div>
      <div class="now-showing__list-item movie">
        <img src="https://fwcdn.pl/fpo/66/50/836650/7926222.3.jpg" alt="" class="movie__image">
        <div class="movie__title">Czarna wdowa</div>
        <div class="movie__info">138 min</div>
        <div class="movie__info">Od 6 maja</div>
        <router-link to="/get-ticket">
          <button class="btn--small">Kup bilet</button>
        </router-link>
      </div>
      <div class="now-showing__list-item movie">
        <img src="https://fwcdn.pl/fpo/66/50/836650/7926222.3.jpg" alt="" class="movie__image">
        <div class="movie__title">Czarna wdowa</div>
        <div class="movie__info">138 min</div>
        <div class="movie__info">Od 6 maja</div>
        <router-link to="/get-ticket">
          <button class="btn--small">Kup bilet</button>
        </router-link>
      </div>
      <div class="now-showing__list-item filters">
        <h3 class="filters__title">Więcej...</h3>
        <button class="filters__category">Wszystkie filmy</button>
        <button class="filters__category">Premiera</button>
        <button class="filters__category">Wkrótce</button>
        <input type="text" placeholder="Szukaj" class="filters__search">
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'NowShowing',
  setup() {
    
  },
}
</script>

<style lang="scss">
.now-showing {
  &__list {
    display: flex;
    margin: 20px 0;
  }

  &__list-item {
    width: 20%;
  }
}

.movie {
  padding: 15px;
  border-radius: 3px;
  transition: background-color 0.2s;

  &:hover {
    background-color: $grey;
  }

  &__image {
    width: 100%;
  }

  &__title {
    font-weight: bold;
  }

  &__info {
    font-size: 0.75em;
    color: darken($text-color, 30%);

    &:last-of-type {
      margin-bottom: 15px;
    }
  }
}

.filters {
  padding: 0 15px;

  &__title {
    margin: 0;
  }

  &__search {
    border: 1px solid darken($text-color, 70%);
    border-radius: 3px;
    background-color: transparent;
    padding: 8px 5px;
    width: 100%;
    text-transform: uppercase;
    color: darken($text-color, 30%);
    font-size: 0.7em;
    font-weight: bold;

    &:focus {
      outline: 0;
      border-color: $primary-color;
    }
  }

  &__category {
    display: block;
    transition: background-color 0.3s;
    margin: 20px 0;
    border: 0;
    border-radius: 3px;
    background-color: $grey;
    cursor: pointer;
    padding: 8px 20px;
    text-transform: uppercase;
    letter-spacing: 2px;
    color: $text-color;
    font-size: 0.7em;
    font-weight: bold;

    &:hover {
      background-color: darken($grey, 5%);
    }
  }
}
</style>