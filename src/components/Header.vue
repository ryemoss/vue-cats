<template>
  <div class="appheader">
    <h1>{{ head }}</h1>
    <h4>{{ underhead }}</h4>
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
.appheader{
  height: 120px;
  background-color: dimgray;
  margin: 0;
}
</style>
