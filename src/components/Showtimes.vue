<template>
  <section class="section showtimes">
    <div class="showtimes__info">
      <div class="section__subtitle">Seanse</div>
      <h2 class="section__title"><strong>Obejrzyj</strong> film</h2>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Molestias delectus ratione nam in, placeat itaque perspiciatis deserunt hic voluptates eius necessitatibus sunt nihil, dolores similique explicabo dolor ipsum totam optio.</p>
    </div>
    <div class="showtimes__table">
      <ul class="showtimes__list">
        <li class="showtimes__list-item" v-for="screening in screenings" :key="screening._id">
          <div class="showtimes__item-time">{{ time(screening.date) }}</div>
          <div class="showtimes__item-title">{{ screening.movie.title }}</div>
          <div class="showtimes__item-info">
            <template v-if="screening.movie.duration">{{ screening.movie.duration }} min - </template>
            <template v-if="screening.movie.genre">{{ screening.movie.genre }}</template>
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
import axios from 'axios';
import { inject, reactive, toRefs } from 'vue';

export default {
  name: 'Showtimes',
  setup() {
    const state = reactive({
      screenings: []
    });

    const time = date => {
      const dateObj = new Date(date);
      return `${dateObj.getHours() < 10 ? '0' : ''}${dateObj.getHours()}:${dateObj.getMinutes() < 10 ? '0' : ''}${dateObj.getMinutes()}`;
    };

    axios.get(`${inject('API_URL')}/next-screenings`).then(response => {
      state.screenings = response.data;
    });

    return { ...toRefs(state), time };
  }
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
    grid-template-columns: min-content 1fr;
    margin: 15px 0;
  }

  &__item-time {
    grid-area: time;
    color: $primary-color;
    font-size: 1.1em;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0 30px;
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