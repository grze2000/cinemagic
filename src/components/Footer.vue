<template>
  <footer class="footer">
    <p>Copyright &copy; 2021 <a href="https://grzegorzbabiarz.com/">Grzegorz Babiarz</a></p>
    <p>Ta strona jest częścią <a href="https://webuniverse.grzegorzbabiarz.com/">Web Universe</a></p>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style lang="scss">
.footer {
  background-image: url('/img/footer.jpg');
  background-position: center top;
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 350px;
}
</style>