<template>
<div>
    <div class="randomgifcat">
        <h1> Random Gif Cat</h1>
    </div>

      <section class="form">
        <label for="titulo">Titulo: </label><br>
        <input type="text" id="titulo" name="titilo" placeholder="Titulo Gif"><br>
        <label for
    </section>

</div>
</template>

<script>
export default {
    name: 'randomgifcat-component',
    // props: {},
    data: function(){
        return {}
    },
    // computed: {},
    methods: {
        // -- Metodos
    },
    //components: {},
}
</script>

<style scoped>
    .randomgifcat{
        padding:15px;
        margin:0 auto;
        background-color:lightblue;
        font-family: 'Montserrat', sans-serif;
        text-align: center;
    }

    .form{
        padding:15px;
        margin:0 auto;
        background-color:pink;
        display:flex;
        justify-content: center;
    }
</style>