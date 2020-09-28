<template>
<div class="main-container">
    <div class="randomgifcat">
        <h1> Random Gif Cat</h1>
    </div>
    <div class="d-flex justify-content-center align-items-center p-4 " style="background-color:pink;">
        <form>
    
        <div class="form-group row">
            <label for="title" class="col-sm-2 col-form-label"><small>Titulo</small></label>
            <div class="col-sm-10">
            <input type="text" class="form-control" id="" placeholder="Titulo" v-model="titulo">
            </div>
        </div>

        <div class="form-group row">
            <label for="filter" class="col-sm-2 col-form-label"><small>Filtro</small></label>
            <div class="col-sm-10">
            <select class="form-control" id="exampleFormControlSelect1" @change="changeFilter($event)">
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
            <select class="form-control" id="exampleFormControlSelect1" @change="changeColor($event)">
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

    <div class="gifcat">
        <button type="button" class="btn btn-light" @click="GetGifCat">Obtener Gif Cat</button>
        
    <div class="gifimg">
        <img :src="gifurl">
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
            },
            gifurl:"",
            selected:"",
        }
    },
    // computed: {},
    methods: {
        changeColor(e){
            //alert(e.target.value); //estoy capturando el evento
            this.dotStyle.background = e.target.value
        },
        changeFilter(e){
            //alert(e.target.value); //capturando evento
            var resp = e.target.value;
            if(resp === "blur"){
                this.selected = "blur"
            }
            else if(resp === "mono"){
                this.selected = "mono"
            }
            else if(resp === "sepia"){
                this.selected = "sepia"
            }
            else if(resp === "negative"){
                this.selected = "negative"
            }
            else if(resp === "paint"){
                this.selected = "paint"
            }
            else if(resp === "pixel"){
                this.selected = "pixel"
            }
            return
            selected, gifurl
        },
        GetGifCat:function(){
        //alert("Obteniendo gatito")
        if(this.titulo === ""){
            alert("Ingresa un título")
        }
        else if(this.tamano === ""){
            alert("Ingresa tamaño de fuente")
        }
        else
            this.gifurl=`https://cataas.com/cat/gif/says/${this.titulo}?filter=${this.selected}&color=${this.dotStyle.background}&size=${this.tamano}&type=or`
        },
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

    .gifcat{
        padding:15px;
        margin:0 auto;
        background-color:lightblue;
        text-align: center;
        height: auto;
        min-height: 300px;
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