<script>
  import TheHeader from "./components/TheHeader.vue";
  import TheFooter from "./components/TheFooter.vue";
  import Card from "./components/Card.vue";
  import axios from "axios";

  export default {
    components:{
      TheHeader,
      TheFooter,
      Card,
    },
    data() {
      return{
        
      }
    },
    
    }
</script>

<template>
  
  <TheHeader></TheHeader>

  <main>
    <router-view></router-view>
  </main>
  
<TheFooter></TheFooter>

</template>

<style lang="scss">
</style>