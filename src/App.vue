<template>
  <div>
    <router-view></router-view>
  </div>
</template>

<script>
import Footer from './components/Footer.vue';
import Header from './components/Header.vue';
import Cats from './components/Cats.vue';
export default {
  components:{
    'app-header': Header,
    'app-footer': Footer,
    'cats': Cats
  },
  data () {
    return {
      title: 'Cats available for adoption'
    }
  },
}

</script>
