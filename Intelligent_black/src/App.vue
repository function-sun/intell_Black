<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <common-header v-if="showHeader"></common-header>
    <router-view :style="showHeader ? 'margin-top:80px;' : ''" />
  </div>
</template>

<script>
import commonHeader from '@/components/commonHeaders.vue'
export default {
  name: 'App',
  components:{
    commonHeader
  },
  data() {
    return {
      showHeader:true,
      loading: true
    }
  },
  watch:{
    $route: {
      handler: function(route) {
        this.showHeader = route.path === '/login' ? false : true
      },
      immediate: true
    }
  },
  methods:{
    
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  /* -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
</style>
