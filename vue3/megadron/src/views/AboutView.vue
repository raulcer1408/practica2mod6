<template>
  <div class="about">
    <template v-for="(valor,index) in productos">
    <div class="container" v-if="index==0">
       <div class="row"> 
       <h3>{{valor.nombre}}</h3> 
      </div>
       <div class="row">    
        <div class="col-12 col-sm-6 col-md-4 ">
        <img v-bind:src="valor.imagen" alt="" width="200">
    </div>
    <div class="col-12 col-sm-6  col-md-8">
      <h6 v-html="valor.descripción"></h6>        
        <div class="p-3 mb-2 text-white" :style="precioEstilos">
            Precio: {{valor.precio}} BOB
        </div>
        <h5>Colores</h5>
        <div>
            <div v-for="color in valor.colores" class="color-box clic" v-bind:style="'background:'+color">
            </div>
        </div>
        <h5>Cantidad</h5>
        <div class="quantity">
            <button v-on:click="">-</button> <div>{{ pedido.cantidad }}</div> <button v-on:click="">+</button>
        </div>
        <div class="buy-box">
            <button v-on:click="" type="button" class="btn btn-primary">Comprar</button>
        </div>
        
    </div>
</div>
</div>
</template>
  </div>

  <div class="container ">

<div class="row">
    <h4>Productos relacionados</h4>
</div>
<div class="row">
    <div class="col">
        <div class="card" style="width: 18rem;">
            <div class="card-body">
                <template v-for="(productoval, index) in productos" :key="index">
                    <div v-if="index==1">
                   <h5 class="card-title" v-if="productoval.nombre==='KF102'">{{productoval.nombre}}</h5>                                    
                   <img v-bind:src="productoval.imagen" alt="" width="200">
                   <p v-if="productoval.descripcion==='Dron plegable KF102 con Gps, 8K, cámara Dual HD, 2 ejes,cardán, Motor sin escobillas, fotografía aérea, 1200M de distancia, novedad de 2022'" class="card-text">{{productoval.descripcion}}</p>
                   <div v-if="productoval.precio==='1180'" class="producto-relacionado-precio">Precio:{{productoval.precio}}</div>
                   <template v-for="valor in productoval.colores">
                   <div v-if="index==1" class="color-box" :style="'background:'+valor"></div>
                  </template>
                </div>
                </template>            
                <div>
             <div>
        </div>
                </div>
            </div>
        </div>
    </div>
    <div class="col">
        <div class="card" style="width: 18rem;">
            <div class="card-body">
                <template v-for="(productoval, index) in productos" :key="index">
                <div v-if="index==2">
                <h5 class="card-title">{{productoval.nombre}}</h5>
                <img v-bind:src="productoval.imagen" alt="" width="200">
                <p  v-if="productoval.descripcion==='KBDFA-Dron E888 RC, cuadricóptero profesional FPV, 4K HD,fotografía aérea, evitación de obstáculos, helicóptero, juguetes de distancia'" class="card-text"> {{productoval.descripcion}}
                </p>
                <div v-if="productoval.precio==='154'" class="producto-relacionado-precio">Precio:{{productoval.precio}} BOB</div>
                </div>
                <template v-for="(valor,index1,el) in productoval.colores">
                    <div v-if="index==2" class="color-box" :style="'background:'+valor"></div>
                   </template> 
                </template>
                <div>
        <div>
        </div>
                </div>
            </div>
        </div>
    </div>
    <div class="col">
        <div class="card" style="width: 18rem;">
            <div class="card-body">
                <template v-for="(productoval, index) in productos" :key="index">
                 <div v-if="index==3">
                    <h5 class="card-title">{{productoval.nombre}}</h5> 
                    <img  :src="productoval.imagen" alt="" width="200">    
                    <p v-if="productoval.descripcion==='Dron Profesional 4K con GPS, 8K, cámara HD, 3 ejes, cardánantivibración, evitación de obstáculos, fotografía aérea, Quadcopter, nuevo'" class="card-text">
                        {{productoval.descripcion}}</p>
                        <div v-if="productoval.precio==='1800'" class="producto-relacionado-precio">Precio:{{productoval.precio}} BOB</div>
                </div>     
                <template v-for="(valor) in productoval.colores">
                    <div v-if="index===3" class="color-box" :style="'background:'+valor"></div>
                   </template>   
                </template>
                <div>
        <div>
        </div>
                </div>
            </div>
        </div>
    </div>
</div>
</div>
</template>

<script>
export default {
  name: 'About',
  data(){
    const appName=process.env.VUE_APP_NAME;
    const api=process.env.VUE_APP_API;
    return {
      appName,
      api,
      precioEstilos: "background: orangered; color: white; font-weight: bold",
      productos:[],
      pedido:
               {
                id:null,
                cantidad: 1,
                color:null
               }
    }
  },
  methods:{
    getProductos(){
      this.axios({
                method: 'get',
                url:  this.api+'/Productos'
            })
                .then((response) => {
                    this.productos = response.data;
                    console.log(response);
                })
                .catch((error) => { console.log(error) })
                .finally(() => { });
    }
  },
  mounted(){
    this.getProductos();
  }
}
</script>
<style >
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

            .quantity button{
                border-radius: 50%;
                display: inline-block;
                width: 30px;
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
            footer {
                
                text-align: center;
                padding: 30px 10px;
                margin-top: 50px;
                min-height: 100px;
            }
            .container{
                margin-top: 50px;
            }
            .producto-relacionado-precio{
                background: orangered;
                color: white;
                text-align: center;
                padding: 10px; 
            }
  </style>