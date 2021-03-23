<template>
  <section class="section coming-soon" v-if="movie">
    <div class="coming-soon__image-wrapper">
      <img :src="movie.poster" alt="" class="coming-soon__image">
    </div>
    <div class="coming-soon__movie-info">
      <div class="section__subtitle">Wkrótce</div>
      <h2 class="section__title">{{ movie.title }}</h2>
      <p>{{ movie.description }}</p>
      <router-link to="/movie/123">
        <button class="btn--filled">Zobacz zwiastun</button>
      </router-link>
      <router-link to="/coming-soon" class="mt-2">
        <button class="btn">Wszystkie nadchodzące premiery</button>
      </router-link>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ComingSoon',
  props: ['movie'],
  setup() {
    
  },
}
</script>

<style lang="scss">
.coming-soon {
  display: flex;
  padding: 0 10%;

  &__image {
    max-width: 350px;
  }

  &__movie-info {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding-left: 50px;
  }
}
</style>