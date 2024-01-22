<script >


export default {
    data() {
        return {
            
            
        }
    },
    methods:{

    },
    props:{
        cards: Object
    }
    
}
</script>

<template>
    <main class="container">
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
            margin-top: 10px;
        }
        
    }
}

</style>