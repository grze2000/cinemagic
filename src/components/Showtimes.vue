<template>
  <section class="section showtimes">
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
      <router-link to="/get-ticket" class="showtimes__button">
        <button class="btn--filled">Kup bilet</button>
      </router-link>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Showtimes',
  setup() {
    
  },
}
</script>

<style lang="scss">
.showtimes {
  display: flex;
  padding: 0 10%;
  position: relative;

  &__table, &__info {
    width: 50%;
    margin: 15px;
  }

  &__table {
    border: 3px solid darken($primary-color, 25%);
    border-radius: 3px;
    padding: 30px 0;
    box-sizing: border-box;
    font-weight: bold;
    position: relative;
  }

  &__button {
    display: inline-block;
    transform: translateY(50%);
    position: absolute;
    bottom: 0;
    right: 10%;
  }

  &__list {
    list-style-type: none;
    padding: 0;
    margin: 0;
  }

  &__list-item {
    display: grid;
    grid-template:  "time title title"
                    "time info info";
    margin: 15px 0;
  }

  &__item-time {
    grid-area: time;
    color: $primary-color;
    font-size: 1.1em;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  &__item-title {
    grid-area: title;
    font-size: 1.2em;
  }

  &__item-info {
    grid-area: info;
    color: darken($text-color, 30%);
    font-size: 0.9em;
  }
}
</style>