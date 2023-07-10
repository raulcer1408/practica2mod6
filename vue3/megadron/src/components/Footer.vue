<template>
    <div>
        <footer :style="'background-color:'+footerColor">
          <p>pie de pagina</p>    
        </footer>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Footer',
    data(){
       return {
        footerColor: "slategrey"
       }
    },
    created() {
        
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
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