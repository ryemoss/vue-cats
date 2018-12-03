<template>
  <footer>
    <p>
      {{ copyright }}
    </p>
  </footer>
</template>

<script>
export default {
  data () {
    return {
      copyright: 'Copyright 2018 VueJSCats'
    }
  },
}
</script>

<style scoped>
  footer{
    display: flex;
    font-size: 12px;
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 60px;
    color: #666;
    background-color: #222;
    justify-content: center;
    align-items: center;
  }
</style>
