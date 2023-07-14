<template>
    <div class="container">

<div class="row">
    <div class="col s12 m6 l4">
        <h6>{{ jsonData?.[0]?.nombre }}</h6>
        <img :src="jsonData?.[0]?.imagen">
    </div>
    <div class="col s12 m6 l8">
        <h6>{{ jsonData?.[0]?.descripcion }}</h6>
        <div class="card-panel caja_precio"> Precio: {{ jsonData?.[0]?.precio }} BOB </div>
        <div class="left">
            <h5>Color</h5>
                <div v-for="items in jsonData?.[0]?.colores" class="col"> 
                <div class="color-box clic" v-on:click="pedido.color=items" :style="{background: items}"></div>
            </div>
            <h5>Cantidad</h5>
            <div class="quantity">
                            <button v-on:click="pedido.cantidad -=1" :disabled="pedido.cantidad<=0">-</button>
                            <div v-if="pedido.cantidad>=0">{{pedido.cantidad}}</div>
                            <div v-else>0</div>
                          <button v-on:click="pedido.cantidad +=1">+</button>
                    </div>
                    <div class="buy-box">
                        <button type="button" class="btn btn-primary" :disabled="pedido.cantidad<=0" v-on:click="comprarAlgo()"
              >
                Comprar
              </button>
                    </div>
        </div>
        
    </div>
</div>
</div>
</template>


<style>
.quantity div{
    text-align: center;
    min-width: 30px;
    display: inline-block;
    font-weight: bold;
}
.buy-box{
    margin: 20px;
}
.quantity button{
    border-radius: 50%;
    display: inline-block;
    width: 30px;
}
.clic{
    cursor: pointer;
}
.buy-box{
    margin: 20px;
}

.caja_precio{
    background: orangered;
    color: white;
    text-align: left;
}
.color-box {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    margin: 7px;
    display: inline-block;
}
img{
    width: 100%;
}
</style>

<script>
import axios from 'axios';

export default {
  name: 'Producto',
data(){
    return{
        jsonData: null,
        active: true,
          pedido: {
            id: null,
            cantidad: 0,
            color: null,
          },
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
 },
        methods: {
          comprarAlgo() {
            if(this.pedido.color!=null){
                this.pedido.id=this.jsonData[0].id
                alert('Producto: '+this.pedido.id+'\nCantidad: '+this.pedido.cantidad+'\nColor seleccionado: '+this.pedido.color)
            }
          }
        }
}
</script>