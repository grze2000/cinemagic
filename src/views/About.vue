<template>
  <Header>
    <template v-slot:title>
      Filmy
    </template>
    <template v-slot:default>
      <router-link to="/about">
       <button class="btn--filled">Seanse</button>
      </router-link>
    </template>
  </Header>
</template>

<script>
import Header from '@/components/Header.vue';

export default {
  name: 'About',
  components: {
    Header
  }
}
</script>
