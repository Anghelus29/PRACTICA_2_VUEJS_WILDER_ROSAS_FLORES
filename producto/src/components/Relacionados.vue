<template>
<div class="container">

<div class="row">
    <h4 class="sub">Productos relacionados</h4>
</div>

<div class="caja">
    <div class="col s12 Relacional">
        <div class="card" style="width: 18rem;">
            <div class="card-content">
                <span class="card-title sub">{{ jsonData?.[1]?.nombre }}</span>
                <img :src="jsonData?.[1]?.imagen">
                <p class="card-text">{{ jsonData?.[1]?.descripcion }}</p>
                <div class="producto-relacionado-precio"> Precio: {{ jsonData?.[1]?.precio }} BOB </div>
                <div v-for="items in jsonData?.[1]?.colores" class="col"> 
                <div class="color-box clic" :style="{background: items}"></div>
            </div>
            </div>
        </div>
    </div>


    <div class="col s12 Relacional">
        <div class="card" style="width: 18rem;">
            <div class="card-content">
                <span class="card-title sub">{{ jsonData?.[2]?.nombre }}</span>
                <img :src="jsonData?.[2]?.imagen">
                <p class="card-text">{{ jsonData?.[2]?.descripcion }}</p>
                <div class="producto-relacionado-precio"> Precio: {{ jsonData?.[2]?.precio }} BOB </div>
                <div v-for="items in jsonData?.[2]?.colores" class="col"> 
                <div class="color-box clic" :style="{background: items}"></div>
            </div>
            </div>
        </div>
    </div>


    <div class="col s12 Relacional">
        <div class="card" style="width: 18rem;">
            <div class="card-content">
                <span class="card-title sub">{{ jsonData?.[3]?.nombre }}</span>
                <img :src="jsonData?.[3]?.imagen">
                <p class="card-text">{{ jsonData?.[3]?.descripcion }}</p>
                <div class="producto-relacionado-precio"> Precio: {{ jsonData?.[3]?.precio }} BOB </div>
                <div v-for="items in jsonData?.[3]?.colores" class="col"> 
                <div class="color-box clic" :style="{background: items}"></div>
            </div>
            </div>
        </div>
    </div>


</div>
</div>
</template>

<style>
.color-box {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    margin: 7px;
    display: inline-block;
}

.clic{
    cursor: pointer;
}
.sub{
    text-align: center;
}
.quantity button{
    border-radius: 50%;
    display: inline-block;
    width: 30px;
}
.col{
    display: inline-block;
}
.quantity div{
    text-align: center;
    min-width: 30px;
    display: inline-block;
    font-weight: bold;
}
.buy-box{
    margin: 20px;
}
.Relacional{
    margin-left: 20px;
    margin-right: 20px;
}
footer {
    
    text-align: center;
    padding: 30px 10px;
    margin-top: 50px;
    min-height: 100px;
}
.producto-relacionado-precio{
    background: orangered;
    color: white;
    text-align: center;
    padding: 10px; 
}
.caja_precio{
    background: orangered;
    color: white;
    text-align: left;
}
.caja
{
    display: flex;
    justify-content: center;
}
</style>

<script>

import axios from 'axios';

export default {
  name: 'Producto',
data(){
    return{
        jsonData: null,
    };
},
 created(){
    axios.get('http://localhost:3000/productos')
    .then(res => {
        console.log(this.jsonData=res.data);
    })
    .catch(error=>{
        console.log(error);
    })
 }

}
</script>