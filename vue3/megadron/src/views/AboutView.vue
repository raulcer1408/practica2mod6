<template>
  <productoc></productoc>  
  <productosrel></productosrel>
</template>

<script>
import productoc from '@/components/productoc.vue';
import productosrel from '@/components/productosrel.vue';
export default {
  name: 'About',
  data(){
    const appName=process.env.VUE_APP_NAME;
    const api=process.env.VUE_APP_API;
    return {
      appName,
      api,
      idenviado:null,
    }
  },
  methods:{
    asignarvalor(id){
       this.idenviado=id;
    }
  },
  components:{
    productoc,productosrel
  },
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