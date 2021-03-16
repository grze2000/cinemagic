<template>
  <section class="section coming-soon">
    <div class="coming-soon__image-wrapper">
      <img src="https://fwcdn.pl/fpo/66/50/836650/7926222.3.jpg" alt="" class="coming-soon__image">
    </div>
    <div class="coming-soon__movie-info">
      <div class="section__subtitle">Wkrótce</div>
      <h2 class="section__title">Czarna wdowa</h2>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Soluta, corporis officia! Quasi optio commodi quidem ipsam voluptas. Porro cum harum et, placeat, quasi, facere tempora incidunt ducimus veritatis ab odio?</p>
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