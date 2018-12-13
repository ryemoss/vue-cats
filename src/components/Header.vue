<template>
  <div class="appheader">
    <h1>{{ head }}</h1>
    <h4>{{ underhead }}</h4>
    <nav>
      <button class="weblink" onclick="window.location.href='/'">HOME</button>
      <button class="weblink" onclick="window.location.href='/directory'">DIRECTORY</button>
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
