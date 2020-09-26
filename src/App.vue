<template>
    <div id="app">
    <randomgifcat></randomgifcat>
    </div>
</template>

<script>
import RandomGifCat from "./components/RandomGifComponent.vue"
export default {
    name: 'component-name',
    // props: {},
    data: function(){
        return {
            message:'Random Gif Cat',
        }
    },
    // computed: {},
    methods: {
        // -- Metodos
    },
    components: {
        'randomgifcat':RandomGifCat,
    },
}
</script>

<style>

body{
    margin:0;
    padding:0;
    box-sizing: border-box;
     font-family: 'Montserrat', sans-serif;
}

</style>
