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
    <main>
        <ul>
            <li v-for="(card, i) in cards" >
                {{ card.name }}
            </li>
        </ul>
    </main>
    
  
</template>

<style lang="scss" scoped>

</style>