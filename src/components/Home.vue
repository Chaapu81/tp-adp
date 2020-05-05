<template>
  <div id="home">
      <navbar :darkMode="darkMode"
              @mode="changeMode"/>
      <main>

      </main>
  </div>
</template>

<script>
import Nav from '@/components/Nav';
export default {
  name: 'home',
  components:{
      'navbar': Nav,
  },

  data: function(){
      return {
          darkMode: false,
      }
  },

  methods:{
    changeMode(){
      this.darkMode = !this.darkMode;
    }
  },

}
</script>

<style scoped>

#home{
  width: 100%;
  height: 100vh;
}

main{
  width: 100%;
  height: calc(100vh - 56px);
  
}

</style>