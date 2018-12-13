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

<style>
body{
  font-family: 'Open Sans', sans-serif;
  letter-spacing: 0.05em;
  text-align: center;
  padding: 0;
  margin: 0;
}
h1,h2,h3{
  margin: 12px;
}
h1{
  font-weight: 200;
}
h3{
  color: #555;
  font-weight: 200;
}
.appmain{
  position: relative;
  min-height: calc(100vh - 80px);
  padding-bottom: 80px;
}
.banner{
  display: flex;
  align-items: center;
  justify-content: center;
  height: 80px;
}
</style>
