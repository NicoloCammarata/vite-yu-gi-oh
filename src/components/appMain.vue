<script >
import axios from 'axios';

export default {
    data() {
        return {
            cards:[],
            searchArchetype: ''
            
        }
    },
    methods:{
        findArchetype(){
            let queryString = ''

            if(this.searchArchetype.length > 0){
                queryString = '?archetype=' + this.searchArchetype;
            }
            axios
                .get('https://db.ygoprodeck.com/api/v7/cardinfo.php' + queryString)
                .then((response) => { 
                    console.log(response)             
                    console.log(response.data.data);
                    this.cards = response.data.data
                
                });
            
                
            
        }

    },
    props:{
        cards: Object
    }
    
}
</script>

<template>
    <main class="container">
        <form @submit.prevent="findArchetype()" class="row g-3">
            <select v-model="searchArchetype" id="inputState" class="form-select w-25 d-inline p-2">
            <option selected>Choose...</option>
            <option value="Alien">Alien</option>
            <option value="Infernoble Arms">Infernoble Arms</option>
            <option value="Nobel Knight">Nobel Knight</option>
            </select>
            <button>
            search
            </button>

        </form>
        
        <ul class="row">
            <div>
                found 39 cards

            </div>
            <li v-for="(card, i) in cards" class="col-3 p-0 ">
                <div class="w-100">
                    <img :src="card.card_images[0].image_url" class="w-100" alt="">
                
                    <div class="text-center">{{ card.name }}</div>
                    <h4 class="text-center">{{ card.archetype }}</h4>
                </div>
            </li>
        </ul>
    </main>
    
  
</template>

<style lang="scss" scoped>
main{
    background-color: orange;
    padding: 50px;
    ul{
        padding: 40px;
        background-color: aliceblue;
        > div{
            height: 50px;
            background-color: black;
            color: white;
            display: flex;
            align-items: center;
            padding-left: 25px;
            width: 100%;

        }
        li{
            list-style: none;
            background-color: orange;
            padding: 0 15px;
            margin-bottom: 10px;
        }
        
    }
}

</style>