<template>
  <footer>
    <p>
      {{ copyright }} <a href="https://github.com/ryemoss/vue-cats" target='blank'>VueJSCats</a>
    </p>
  </footer>
</template>

<script>
export default {
  data () {
    return {
      copyright: 'Copyright © 2018 '
    }
  },
}
</script>

<style scoped>
a{
  background-color: none;
  text-decoration: none;
  color: #777;
}
</style>
