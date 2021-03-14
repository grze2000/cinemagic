<template>
  <Header>
    <template v-slot:title>
      Witaj w kinie Cinemagic
    </template>
    <template v-slot:default>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
      <router-link to="/about">
       <button class="btn--filled">Repertuar</button>
      </router-link>
    </template>
  </Header>
  <main class="main">
    <section class="content">
      <button class="btn">Repertuar</button>
      <button class="btn">Kup bilet</button>
      <button class="btn">Cennik</button>
    </section>
    <section class="now-showing">
      <div class="section__subtitle">Filmy</div>
      <h2 class="section__title"><strong>Aktualnie</strong> wyświetlane</h2>
      <div class="now-showing__list">
        <div class="now-showing__list-item movie">
          <img src="" alt="" class="movie__image">
          <div class="movie__title">Czarna wdowa</div>
          <div class="movie__duration">138 min</div>
          <div class="movie__release">Od 6 maja</div>
          <router-link to="/get-ticket">
            <button class="btn">Get ticket</button>
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
    <section class="coming-soon">
      <div class="coming-soon__image-wrapper">
        <img src="" alt="" class="coming-soon__image">
      </div>
      <div class="coming-soon__movie-info">
        <div class="section__subtitle">Wkrótce</div>
        <h2 class="section__title">Czarna wdowa</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Soluta, corporis officia! Quasi optio commodi quidem ipsam voluptas. Porro cum harum et, placeat, quasi, facere tempora incidunt ducimus veritatis ab odio?</p>
        <router-link to="/movie/123">
          <button class="btn--filled">Zobacz zwiastun</button>
        </router-link>
        <router-link to="/coming-soon">
          <button class="btn--">Wszystkie nadchodzące premiery</button>
        </router-link>
      </div>
    </section>
    <section class="showtimes">
      <div class="showtimes__info">
        <div class="section__subtitle">Seanse</div>
        <h2 class="section__title"><strong>Obejrzyj</strong> film</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Molestias delectus ratione nam in, placeat itaque perspiciatis deserunt hic voluptates eius necessitatibus sunt nihil, dolores similique explicabo dolor ipsum totam optio.</p>
      </div>
      <div class="showtimes__table">
        <ul class="showtimes__list">
          <li class="showtimes__list-item">
            <div class="showtimes__item-time">12:00</div>
            <div class="showtimes__item-title">Czarna wdowa</div>
            <div class="showtimes__item-info">
              Akcja/Sci-Fi - 138 min - USA
            </div>
          </li>
          <li class="showtimes__list-item">
            <div class="showtimes__item-time">14:00</div>
            <div class="showtimes__item-title">Czarna wdowa</div>
            <div class="showtimes__item-info">
              Akcja/Sci-Fi - 138 min - USA
            </div>
          </li>
          <li class="showtimes__list-item">
            <div class="showtimes__item-time">17:00</div>
            <div class="showtimes__item-title">Czarna wdowa</div>
            <div class="showtimes__item-info">
              Akcja/Sci-Fi - 138 min - USA
            </div>
          </li>
          <li class="showtimes__list-item">
            <div class="showtimes__item-time">19:00</div>
            <div class="showtimes__item-title">Czarna wdowa</div>
            <div class="showtimes__item-info">
              Akcja/Sci-Fi - 138 min - USA
            </div>
          </li>
          <li class="showtimes__list-item">
            <div class="showtimes__item-time">21:00</div>
            <div class="showtimes__item-title">Czarna wdowa</div>
            <div class="showtimes__item-info">
              Akcja/Sci-Fi - 138 min - USA
            </div>
          </li>
        </ul>
        <router-link to="/get-ticket">
          <button class="btn--filled">Kup bilet</button>
        </router-link>
      </div>
    </section>
    <section class="movie-pass">
      <div class="movie-pass__info">
        <div class="section__subtitle">Promocje</div>
        <h2 class="section__title">Płać mniej ze zniżkami grupowymi i karnetami</h2>
        <router-link to="/movie-pass">
          <button class="btn-filled">Sprawdź</button>
        </router-link>
      </div>
      <img src="" alt="" class="movie-pass__image">
      <img src="" alt="" class="movie-pass__image">
      <img src="" alt="" class="movie-pass__image">
      <img src="" alt="" class="movie-pass__image">
    </section>
  </main>
</template>

<script>
import Header from '@/components/Header.vue';

export default {
  name: 'Home',
  components: {
    Header
  }
}
</script>

<style lang="scss">

</style>