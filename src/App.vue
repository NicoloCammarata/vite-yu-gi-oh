<script >
import appHeader from './components/appHeader.vue';
import appMain from './components/appMain.vue';
import appFooter from './components/appFooter.vue';
import axios from 'axios';
import { store } from './store'

export default {
    data() {
        return {
            store,

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
                .get(this.store.url)
                .then((response) => { 
                    console.log(response)             
                    console.log(response.data.data);
                    this.store.cards = response.data.data
                
                });
            
        
    }
  
}
</script>

<template>

  
  <appHeader />

  <appMain />
  

  <appFooter />
  
</template>

<style lang="scss" >
@use "assets/scss/main" as *;
@import "assets/scss/partials/reset";

</style>
