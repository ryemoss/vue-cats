<template>
  <div class="appheader">
    <h1>{{ head }}</h1>
    <h4>{{ underhead }}</h4>
    <nav>
      <router-link class="weblink" to="/">HOME</router-link>
      <router-link class="weblink" to="/directory">DIRECTORY</router-link>
    </nav>
  </div>
</template>

<script>
export default {
  data () {
    return {
      head: 'MOSSY HOMES',
      underhead: 'Cat Adoption Center'
    }
  },
}
</script>

<style scoped>
h1{
  color: white;
  padding: 0;
  margin: 0;
  font-weight: 200;
}
h4{
  color: white;
  font-weight: 200;
  margin: 14px;
}
</style>
