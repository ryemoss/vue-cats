<template>
  <div>
    <app-header></app-header>
    <h1>Welcome to the MOSSY HOMES cat adoption center!</h1>
    <h2>Check out our directory to see the amazing cats we have available for adoption today.</h2>
    <button onclick="window.location.href='/directory'">COME SEE</button>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Footer from './Footer.vue';
import Header from './Header.vue';

export default {
  components:{
    'app-header': Header,
    'app-footer': Footer,
  },
  data () {
    return {
      copyright: 'Copyright 2018 VueJSCats'
    }
  },
}
</script>

<style scoped>
h1{
  margin: 80px;
  font-weight: 400;
}
h2 {
  font-weight: 200;
}
button{
  font-size: 24px;
  margin-top: 75px;
  width: 50%;
  max-width: 340px;
  height: 60px;
  border: none;
  background: #222;
  color: white;
  font-family: inherit;
}

</style>
