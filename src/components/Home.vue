<template>
  <div>
    <app-header></app-header>
    <div class="flex">
      <h1>Welcome to the MOSSY HOMES cat adoption center!</h1>
      <h2>Check out our directory to see the amazing cats we have available for adoption today.</h2>
      <router-link class="themedbutton" to="/directory">COME SEE</router-link>
    </div>
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
