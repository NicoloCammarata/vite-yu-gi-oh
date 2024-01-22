<script >
import appHeader from './components/appHeader.vue';
import appMain from './components/appMain.vue';
import appFooter from './components/appFooter.vue';
import axios from 'axios';


export default {
    data() {
        return {
            cards:[]

        }
    },
    methods:{

    },
    components: {
        appHeader,
        appMain,
        appFooter,
        axios

    },
    mounted() {
        axios
            .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
            .then((response) => { 
                console.log(response)             
                console.log(response.data.data);
                this.cards = response.data.data
            });
        
    }
  
}
</script>

<template>

  
  <appHeader />

  <appMain 
  :cards = cards
  />
  

  <appFooter />
  
</template>

<style lang="scss" >
@use "assets/scss/main" as *;
@import "assets/scss/partials/reset";

</style>
