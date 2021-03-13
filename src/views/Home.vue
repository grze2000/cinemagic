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