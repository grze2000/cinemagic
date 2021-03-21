<template>
  <router-view/>
  <Footer></Footer>
</template>

<script>
import Footer from '@/components/Footer.vue';
import { provide } from 'vue';

export default {
  components: {
    Footer
  },
  setup() {
    provide('API_URL', 'http://localhost:3000');
  },
  watch: {
    $route(to) {
      document.title = to.meta.title || 'Cinemagic';
    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;700&display=swap');

body {
  margin: 0;
  background-color: #000;
  background-image: url('/img/background.jpg');
  background-position: center top;
  background-repeat: no-repeat;
  background-size: 100% auto;
  min-height: 800px;
  color: $text-color;
  font-family: 'Poppins', sans-serif;
}
</style>
