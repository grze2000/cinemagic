<template>
  <section class="section now-showing">
    <div class="section__subtitle">Filmy</div>
    <h2 class="section__title"><strong>Aktualnie</strong> wyświetlane</h2>
    <div class="now-showing__list">
      <div class="now-showing__list-item movie" v-for="movie in movies" :key="movie._id">
        <span class="movie__ribbon--coming-soon" v-if="new Date(movie.release) > new Date()">Wkrótce</span>
        <span class="movie__ribbon--premiere" v-if="isPremiere(movie.release)">Premiera</span>
        <img :src="movie.poster" alt="" class="movie__image">
        <div class="movie__title">{{ movie.title }}</div>
        <div class="movie__info">{{ movie.duration ? `${movie.duration} min` : movie.genre }}</div>
        <div class="movie__info">{{ releaseDate(movie.release) }}</div>
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
  props: {
    movies: {
      type: Array,
      default: () => []
    }
  },
  setup() {
    const months = ['stycznia', 'lutego', 'marca', 'kwietnia', 'maja', 'czerwca', 'lipca', 'sierpnia', 'września', 'października', 'listopada', 'grudnia'];
    const releaseDate = date => {
      const dateObj = new Date(date);
      return `od ${dateObj.getDate()} ${months[dateObj.getMonth()]}`;
    }

    const isPremiere = releaseDate => {
      const release = new Date(releaseDate);
      const date = new Date();
      date.setDate(date.getDate() - 2);
      return release > date && release < new Date();
    }

    return { releaseDate, isPremiere };
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
  position: relative;

  &:hover {
    background-color: $grey;
  }

  &__image {
    width: 100%;
    box-shadow: 0 0 15px 5px rgba(32,32,32,0.5);
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

  &__ribbon {
    position: absolute;
    top: 25px;
    right: 8px;
    box-shadow: -12px 0px 15px 5px rgba(32,32,32,0.5);
    padding: 4px 10px 4px 0;
    text-transform: uppercase;
    line-height: 1em;
    letter-spacing: 1px;
    font-size: 11px;
    font-weight: 600;
    user-select: none;
    
    &::after, &::before {
      position: absolute;
      border-style: solid;
      content: '';
    }

    &::before {
      right: 0;
      bottom: 100%;
      border-width: 5px 0 0 7px;
    }

    &::after {
      top: 0;
      right: 100%;
      border-width: calc(.5em + 4px) 8px calc(.5em + 4px) 8px;
    }
  }
}

.movie__ribbon--premiere {
  @extend .movie__ribbon;
  background-color: $primary-color;

  &::before {
    border-color: transparent transparent transparent darken($primary-color, 20%);
  }

  &::after {
    border-color: $primary-color $primary-color $primary-color transparent;
  }
}
.movie__ribbon--coming-soon {
  @extend .movie__ribbon;
  background-color: $secondary-color;

  &::before {
    border-color: transparent transparent transparent darken($secondary-color, 20%);
  }

  &::after {
    border-color: $secondary-color $secondary-color $secondary-color transparent;
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