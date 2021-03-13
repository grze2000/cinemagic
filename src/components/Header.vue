<template>
  <header class="header">
    <nav class="nav">
      <div class="logo">Cinemagic</div>
      <ul class="menu">
        <li v-for="(text, url) in links" :key="url" class="menu__item">
          <router-link :to="url" class="menu__link">{{ text }}</router-link>
        </li>
      </ul>
    </nav>
    <div class="header__content">
      <div class="header__title"><slot name="title"></slot></div>
      <div class="header__slot"><slot></slot></div>
    </div>
  </header>
</template>

<script>
export default {
  setup() {
    const links = {
      '/': 'Strona główna',
      '/#test': 'Repertuar',
      '/about': 'Filmy'
    };
    return {links};
  },
}
</script>

<style lang="scss">
.header {

  &__content {
    padding: 8% 10%;
  }

  &__title {
    text-transform: uppercase;
    font-weight: bold;
    font-size: 6em;
  }
}
.nav {
  box-sizing: border-box;
  display: flex;
  align-items: center;
  padding: 15px 40px;
  width: 100%;
  font-size: 1.1em;
}
.menu {
  display: flex;
  margin: 0 0 0 auto;
  padding: 0;
  list-style-type: none;
  font-weight: 500;

  &__item {
    margin: 0 10px;
  }

  &__link {
    text-decoration: none;
    color: inherit;
    transition: color .3s;

    &:hover {
      color: darken($text-color, 20%);
    }
  }
}
.logo {
  font-size: 1.7em;
  font-weight: bold;
}
</style>