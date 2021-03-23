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
    <section class="section content">
      <button class="btn">Repertuar</button>
      <button class="btn">Kup bilet</button>
      <button class="btn">Cennik</button>
    </section>
    <NowShowing :movies="movies"></NowShowing>
    <ComingSoon :movie="comingSoonMovie"></ComingSoon>
    <Showtimes></Showtimes>
    <MoviePass :movies="movies"></MoviePass>
  </main>
</template>

<script>
import Header from '@/components/Header.vue';
import NowShowing from '@/components/NowShowing.vue';
import ComingSoon from '@/components/ComingSoon.vue';
import Showtimes from '@/components/Showtimes.vue';
import MoviePass from '@/components/MoviePass.vue';
import axios from 'axios';
import { computed, inject, ref } from 'vue';

export default {
  name: 'Home',
  components: {
    Header,
    NowShowing,
    ComingSoon,
    Showtimes,
    MoviePass
  },
  setup() {
    const movies = ref([]);

    axios.get(`${inject('API_URL')}/movies`).then(response => {
      movies.value = response.data;
      console.log(comingSoonMovie.value);
    });

    const comingSoonMovie = computed(() => movies.value.filter(movie => new Date(movie.release) > new Date())[0]);
    
    return { movies, comingSoonMovie };
  }
}
</script>

<style lang="scss">
.main {
  padding: 0 10%;
}

.section {
  margin: 120px 0;

  &__title {
    font-size: 3rem;
    font-weight: normal;
    margin: 0;
  }

  &__subtitle {
    text-transform: uppercase;
    color: $primary-color;
    font-weight: bold;
  }
}

.content {
  text-align: center;
  margin: 50px 0;

  > button {
    margin: 0 5%;
  }
}
.mt-2 {
  margin-top: 20px;
}
</style>