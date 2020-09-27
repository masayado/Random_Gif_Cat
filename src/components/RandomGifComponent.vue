<template>
<div class="main-container">
    <div class="randomgifcat">
        <h1> Random Gif Cat</h1>
    </div>
    <div class="d-flex justify-content-center align-items-center p-4 " style="background-color:pink;">
        <form>
    
        <div class="form-group row">
            <label for="Titulo" class="col-sm-2 col-form-label"><small>Titulo</small></label>
            <div class="col-sm-10">
            <input type="title" class="form-control" id="" placeholder="Titulo">
            </div>
        </div>

        <div class="form-group row">
            <label for="Filtro" class="col-sm-2 col-form-label"><small>Filtro</small></label>
            <div class="col-sm-10">
            <select class="form-control" id="exampleFormControlSelect1">
            <option>1</option>
            </select>
            </div>
        </div>

        <div class="form-group row">
            <label for="Filtro" class="col-sm-2 col-form-label"><small>Color</small></label>
            <div class="col-sm-10">
            <select class="form-control" id="exampleFormControlSelect1">
            <option>1</option>
            </select>
            </div>
        </div>

        <div class="form-group row">
            <label for="Titulo" class="col-sm-2 col-form-label"><small>Tamaño</small></label>
            <div class="col-sm-10">
            <input type="title" class="form-control" id="" placeholder="Tamaño">
            </div>
        </div>
        </form>
        </div>

    <div class="randomgifcat">
        <button type="button" class="btn btn-light" @click="ObtenerGato">Obtener Cat Gif</button>
        <img src="" alt="">
    </div>
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
        ObtenerGato:function(){
            alert("Obteniendo gatito")
        }
    },
    //components: {},
}
</script>

<style scoped>
    .randomgifcat{
        padding:15px;
        margin:0 auto;
        background-color:lightblue;
        text-align: center;
        height: 100%;
    }

</style>