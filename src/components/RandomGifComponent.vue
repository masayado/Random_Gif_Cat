<template>
<div class="main-container">
    <div class="randomgifcat">
        <h1> Random Gif Cat</h1>
    </div>
    <div class="d-flex justify-content-center align-items-center p-4 " style="background-color:pink;">
        <form>
    
        <div class="form-group row">
            <label for="title" class="col-sm-2 col-form-label" v-model="titulo"><small>Titulo</small></label>
            <div class="col-sm-10">
            <input type="text" class="form-control" id="" placeholder="Titulo">
            </div>
        </div>

        <div class="form-group row">
            <label for="filter" class="col-sm-2 col-form-label"><small>Filtro</small></label>
            <div class="col-sm-10">
            <select class="form-control" id="exampleFormControlSelect1">
            <option 
            v-for="filtro in filtros" 
            :key="filtro" 
            :value="filtro" 
            v-text="filtro">
            </option>
            </select>
            </div>
        </div>

        <div class="form-group row">
            <label for="color" class="col-sm-2 col-form-label"><small>Color</small></label>
            <div class="col-sm-8">
            <select class="form-control" id="exampleFormControlSelect1" @change="cambioColor($event)">
            <option 
            v-for="color in colores" 
            :key="color.color" 
            :value="color.value" 
            v-text="color.color">
            </option>
            </select>
            </div>
            <div class="col-sm-2 justify-content-center align-items-center">
                <span :style="dotStyle" class="dot"></span>
            </div>
        </div>

        <div class="form-group row">
            <label for="size" class="col-sm-2 col-form-label"><small>Tamaño</small></label>
            <div class="col-sm-10">
            <input type="text" class="form-control" id="" placeholder="Tamaño" v-model="tamano">
            </div>
        </div>
        </form>
        </div>

    <div class="randomgifcat">
        <button type="button" class="btn btn-light" @click="GetGifCat">Obtener Gif Cat</button>
        
    <div class="gifimg">
    </div>

    </div>

</div>
</template>

<script>
export default {
    name: 'randomgifcat-component',
    // props: {},
    data: function(){
        return {
            titulo:"",
            filtros:["blur", "mono", "sepia", "negative", "paint", "pixel",],
            tamano:"",
            colores:[
                {color:"Rojo", value:"red"},
                {color:"Azul", value: "blue"},
                {color: "Verde", value: "green"},
                {color:"Blanco", value:"white"},
                {color:"Amarillo", value:"yellow"}
            ],
            dotStyle:{
                background:"",
            }
        }
    },
    // computed: {},
    methods: {
        GetGifCat:function(){
        alert("Obteniendo gatito")
        fetch(`https://cataas.com/cat/gif/says/${this.titulo}?filter=filtro&color=color&size=tamaño`)
        .then(response => response.json())
        .then(data => console.log(data));
        },
        cambioColor(e){
            //alert(e.target.value); //estoy capturando el evento
            this.dotStyle.background = e.target.value
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

    .gifimg{
        padding:15px;
    }

    .dot {
    height: 25px;
    width: 25px;
    border-radius: 50%;
    display: inline-block;
    position: relative;
    top: 5px;
    background:red;
    }

</style>